quanlin@quanlin:~/go/src/github.com/kubeflow/tf-operator/cmd/tf-operator.v1$ go install ./...
quanlin@quanlin:~/go/src/github.com/kubeflow/tf-operator$ cp ~/go/bin/tf-operator.v1 ./build/images/quanlin_tf_operator/
quanlin@quanlin:~/go/src/github.com/kubeflow/tf-operator/build/images/quanlin_tf_operator$ docker build -f Dockerfile -t quanlin/tf_operator:$TAG ./
quanlin@quanlin:~/go/src/github.com/kubeflow/tf-operator/build/images/quanlin_tf_operator$ docker push quanlin/tf_operator:190807-1245

docker.io/quanlin/tf_operator:190807-1245
quanlin@quanlin:~/kubeflow/manifests/tf-training/tf-job-operator$ kustomize build base

quanlin@quanlin:~/integration/2019/0807/quanlin.yaml