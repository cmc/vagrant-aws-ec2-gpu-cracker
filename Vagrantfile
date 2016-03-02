Vagrant.configure("2") do |config|
  config.vm.box = "dummy"

  config.vm.provider :aws do |aws, override|
    # this instance type is 4 NVIDIA cards & 32 cores & some SSDs. Ridic.
    # see https://aws.amazon.com/ec2/instance-types/ & https://aws.amazon.com/ec2/pricing/
    aws.instance_type = "g2.8xlarge"
    aws.ami = "ami-9abea4fb"
    aws.region = "us-west-2"

    # define securitygroup in AWS/EC2 Console. Allow SSH inbound.
    aws.security_groups = ["cmc-security-group"]
    aws.tags = {
      'Name' => 'cmc_gpucrack_instance',
    }

    aws.access_key_id = "PUT ACCESS KEY HERE"
    aws.secret_access_key = "PUT PRIV KEY HERE"
    aws.session_token = "PUT SESSION TOKEN HERE"

    # define / create keypair in AWS / EC2 console.
    aws.keypair_name = "cmc_gpucrack"
    override.ssh.username = "ubuntu"
    override.ssh.private_key_path = "PATH TO YOUR .PEM FILE SPECIFIED ABOVE"
  end

     config.vm.provision "shell", path: "install_oclhashcat.sh"

end
