
>[!tldr] Guide on how to use a `id_rsa` key

1. Create a new `id_rsa` file
	1. `sudo nano id_rsa`
2. Next, place the contents from the **stolen-id_rsa** key inside the `id_rsa` you created
```shell
-----BEGIN OPENSSH PRIVATE KEY-----
	<SNIP>
m3MVFR4sN7a1cAAAANZGFuaWVsQEVudGl0eQECAwQFBg==
-----END OPENSSH PRIVATE KEY-----
```
1. Give proper permissions to the file
	1. `sudo chmod 400 id_rsa`
2. Use the key!
	1. `sudo ssh -i id_rsa user@{target-ip}` 

