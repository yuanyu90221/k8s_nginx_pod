# nginx_pod

## introduction

    This is an example of pod structure of the nginx service

## basic concept

    pod is the basic computed unit of an "service"

    all containers in the same pod share the same clusterIp

## how deploy a pod

    kubectl apply -f `${pod-config}`

## how to get pod info

    kubectl  get pods `${podname}` -o json

## how to delete a pod with specific namespace

    kubectl delete -n `${namespace}` pod `${podname}`

## delete a pod by podnanme

    kubectl delete pods/${podname}

## delete a pod by config file

    kubectl delete -f ${pod-config}

## port-forward pod to host

    kubectl port-forward ${podname} ${hostPort}:$${containerPort}

## pod health Check types:

    1 HTTP health check:

        check status by send http request to container if http status in [200, 400] then success, else false

    2 TCP healch check

        check TCP connection to container whether success

    3 Exec health check

        check container status by execute a specific command

## limit the resources of a pod

    