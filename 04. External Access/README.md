#### If you get an error on creating ingress component related to "nginx-controller-admission" webhook, than manually delete the ValidationWebhook and try again. To delete the ValidationWebhook:
    kubectl get ValidatingWebhookConfiguration 
    kubectl delete ValidatingWebhookConfiguration {name}
