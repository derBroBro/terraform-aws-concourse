# AWS VPN aconnection
Terraform module which setup a very generic concourse CI server.
In behind coreOS and docker is used.
* Create instance
* Create EC2 roöle
* OPTIONAL: Add first pipeline


## Usage
```hcl
module "account" {
  source = "zoitech/concourse/aws"
  instance_name = "concourse"
  instance_sg_id = "${aws_security_group.allow_all.id}"
  concourse_username = "concourse"
  concourse_password = "Sup3rS3cur3"
  instance_key_name = "my_key"
  instance_key = "${file("iot-stage-deploy.pem")}"
  instance_subnet_id = "${module.network.sn_public_a_id}"
}
```

## Authors
Module managed by [Zoi](https://github.com/zoitech).

## License
MIT License. See LICENSE for full details.
