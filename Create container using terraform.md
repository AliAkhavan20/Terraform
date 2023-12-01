# Create Container Using Terraform
a simple terraform yaml file.
```
resource "null_resource" "remote_server" {

provisioner "remote-exec" {
    inline = [
      "docker run -d -p 8000:80 --name my-nginx nginx",
    ]
connection {
    type     = "ssh"
    user     = "ali"
    password = "P@ssw0rd"
    host     = "192.168.1.130"
    port     = "2022"
    }
  }
}
```
