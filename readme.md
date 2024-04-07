https://qiita.com/irotoris/items/8d6be7b0afd9b8afc321

##

```sh
gcloud beta compute security-policies create ingress-ip-whitelist --description "ingress-ip-whitelist"

gcloud compute security-policies rules update 2147483647 \
    --security-policy ingress-ip-whitelist \
    --action "deny-403"

gcloud compute security-policies rules create 10000 \
    --security-policy ingress-ip-whitelist \
    --description "allow traffic from 192.0.2.0/24,172.16.3.0/24" \
    --src-ip-ranges "192.0.2.0/24,172.16.3.0/24" \
    --action "allow"
```

