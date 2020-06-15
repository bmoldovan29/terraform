provider "aws" {
}

data "aws_ami" "centos7" {
  most_recent = true

  filter {
    name   = "name"
    values = ["CentOS Linux 7 x86_64 HVM EBS ENA 2002_01-b7ee8a69-ee97-4a49-9e68-afaee216db2e-ami-0042af67f8e4dcc20.4*"]
  }

  filter {
    name   = "virtualization-type"
    values = ["hvm"]
  }

  owners = ["aws-marketplace"] # Canonical
}
resource "aws_instance" "main" {
  ami           = "${data.aws_ami.centos7.id}"
  instance_type = "t2.micro"

  tags = {
    Name = "MyAMI"
  }
}
