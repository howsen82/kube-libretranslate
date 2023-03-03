We can create using the htpasswd tool

```
$ htpasswd /tmp/htpass <user> <password>
$ cat /tmp/htpass | base64
```

```
$ kubectl apply -f libretrans-auth.yaml
$ kubectl apply -f libretranslate.yaml
```

**Test case**
```
$ curl -H "Content-type: application/json" -H "Accept: application/json" -u "user:password" -d '{ "q": "hello world", "source": "en", "target": "es"}' https://trans.example.com
```