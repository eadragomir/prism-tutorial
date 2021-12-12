# Prism Tutorial

This repository serves as a base for a [Prism tutorial published on 11sigma.com blog](https://11sigma.com/blog/2019-10-11--prism-tutorial/).

# Install PRISM

npm install -g @stoplight/prism-cli

# Run Prism mock server

prism mock reference/flight-check-in-step-1/openapi.yaml

# Make a request

curl 127.0.0.1:4010/check-in/passengers

# Run Prism in dynamic mode

prism mock --dynamic reference/flight-check-in-step-3/openapi.yaml

Request: curl 127.0.0.1:4010/check-in/passengers?__dynamic=true

# Select response example by a key

prism mock reference/flight-check-in-step-4/openapi.yaml

curl http://127.0.0.1:4010/check-in/passengers?__example=not-checked-in-passenger

## Proxy mode

prism mock -p 4011 reference/petstore/petstore.yaml
curl localhost:4011/pets/1

prism proxy -p 4010 --errors reference/petstore/petstore_expected.yaml http://localhost:4011
curl http://localhost:4010/pets/1


