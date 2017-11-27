Updated model_spec to include signature_name. This fixed the error `{ Error: input tensor alias not found in signature: images. Inputs expected to be in the set {inputs}.`

# tensorflow-serving-node-client
Node gRPC client for TensorFlow Serving server

```
const fs = require('fs');
const client = require('tensorflow-serving-node-client')('localhost:9000');

const IMAGE_PATH = './cat.jpg';
const buffer = fs.readFileSync(IMAGE_PATH);

client.predict(buffer, (err, res) => {
  if (err) {
    return console.error(err);
  }

  console.log(res);
});
```