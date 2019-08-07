### Simple mnist example with persistent volume

This is a simple example using an MNIST model that outputs a TF summary.
The example also mounts a persistent volume for output, making it suitable
for integrating with other components like Katib.

The source code is borrowed from TensorFlow tutorials [here](https://github.com/tensorflow/tensorflow/blob/master/tensorflow/examples/tutorials/mnist/mnist_with_summaries.py).

To build this image:
```shell
docker build -f Dockerfile -t kubeflow/tf-mnist-with-summaries:1.0 ./
quanlin@quanlin:~/kubeflow/tf-operator/examples/v1beta2/mnist_with_summaries$ docker build -f Dockerfile -t quanlin/tf-mnist-with-summaries:$TAG ./
quanlin@quanlin:~/kubeflow/tf-operator/examples/v1beta2/mnist_with_summaries$ docker push quanlin/tf-mnist-with-summaries:190806-0927

```

Usage:
1. Add the persistent volume and claim: `kubectl apply -f tfevent-volume/.`
1. Deploy the TFJob: `kubectl apply -f tf_job_mnist.yaml`
