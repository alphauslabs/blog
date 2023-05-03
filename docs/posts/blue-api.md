---
date: 2023-05-03
authors:
- flowerinthenight
categories:
- Tech
- API
---

# Blue API

In today's post, I will talk a little bit about [Blue API](https://labs.alphaus.cloud/docs/blueapi/overview/), our public-facing, as well as internal APIs. Blue API allows you to programmatically access our services such as Ripple and WavePro. It uses [protocol buffers](https://protobuf.dev/) for its service and message definitions, and [gRPC](https://grpc.io/) for implementation and server/client stub generation. It also uses [grpc-gateway](https://grpc-ecosystem.github.io/grpc-gateway/) for proxying JSON/REST requests to gRPC, and generating [OpenAPI documentation](https://labs.alphaus.cloud/blueapidocs/). This way, you have the option to use our APIs using either gRPC or JSON/REST, or both.

<!-- more -->

## Structure

Blue API starts with our API definitions. You can find the repository [here](https://github.com/alphauslabs/blueapi). Once compiled, it will generate our main [SDK](https://github.com/alphauslabs/blue-sdk-go) along with the [other SDKs](https://labs.alphaus.cloud/docs/blueapi/client-sdks/) we support. (By the way, if you're a user and have a particular programming language you want supported, contact us at [support@alphaus.cloud](mailto:support@alphaus.cloud) and we will try to prioritize it.) The build also generates our OpenAPI reference documentation [here](https://labs.alphaus.cloud/blueapidocs/). Our team then uses the generated SDK, [blue-sdk-go](https://github.com/alphauslabs/blue-sdk-go) (we use [Go](https://go.dev/) as our main programming language), to implement the necessary gRPC services in the backend. As a client, you can either call our gRPC services directly using the supported SDKs, or call our HTTP proxies through an HTTP client such as `curl`, or any HTTP library which is part of most modern programming languages.

## Authentication

Blue API uses client credentials (tokens) for authentication. You can check this detailed [guide](https://labs.alphaus.cloud/docs/blueapi/authentication/) for more information.

## Usage

Here's an example Go code on how to use the SDK to call our gRPC services directly:

``` golang
ctx := context.Background()
client, _ := iam.NewClient(ctx)
defer client.Close()
out, err := client.WhoAmI(ctx, &iam.WhoAmIRequest{})
log.Println(out, err)
```

Here's another example using `curl` (uses our [bluectl](https://github.com/alphauslabs/bluectl) tool to generate the token):

``` sh
$ curl -H "Authorization: Bearer $(bluectl token)" \
  https://api.alphaus.cloud/m/blue/iam/v1/whoami | jq
```

## Closing

At the moment, Blue API is still a work in progress. Most of the APIs currently supported in Ripple and WavePro are still not available. In the meantime, you can still use our JSON/REST APIs [here](https://docs.alphaus.cloud/v/api-reference/). We plan to upgrade as many of our JSON/REST APIs as possible over to gRPC as it is significantly more efficient in terms of throughput and CPU usage compared to JSON/REST API. However, we don't intend to deprecate our JSON/REST APIs once the transition is completed. You should be able to use both.
