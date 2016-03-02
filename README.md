# vagrant-aws-ec2-gpu-cracker
throws up a 4x beast cuda box w/ 32cores for password cracking, installs cuda drivers &amp; oclhashcat

    # nvidia-smi  -L
    #   GPU 0: GRID K520 (UUID: GPU-17f859aa-09ba-35ec-dbe7-268879cc441a)
    #   GPU 1: GRID K520 (UUID: GPU-d96cf21c-0889-d238-f7d2-53c75dfb79ac)
    #   GPU 2: GRID K520 (UUID: GPU-523b46de-a687-e3f5-cce5-c12da76636c2)
    #   GPU 3: GRID K520 (UUID: GPU-082ddb09-6f7d-bb2d-cc9f-11f6fc6ff4cf)
```
Session.Name...: cudaHashcat
Status.........: Running
Input.Mode.....: Mask (?d?d?d?d?d?d?d) [7] (0.07%)
Hash.Target....: ohai
Hash.Type......: $my_target
Time.Started...: Wed Mar  2 07:45:48 2016 (4 mins, 3 secs)
Time.Estimated.: Wed Mar  2 08:00:59 2016 (2 mins, 2 secs)
Speed.GPU.#1...:     6893 H/s
Speed.GPU.#2...:     6901 H/s
Speed.GPU.#3...:     6899 H/s
Speed.GPU.#4...:     6894 H/s
Speed.GPU.#*...:    27587 H/s
Recovered......: 0/1 (0.00%) Digests, 0/1 (0.00%) Salts
Progress.......: 6684672/10000000 (66.85%)
Rejected.......: 0/6684672 (0.00%)
Restore.Point..: 606208/1000000 (60.62%)
HWMon.GPU.#1...: 96% Util, 68c Temp, N/A Fan
HWMon.GPU.#2...: 96% Util, 59c Temp, N/A Fan
HWMon.GPU.#3...: 96% Util, 76c Temp, N/A Fan
HWMon.GPU.#4...: 96% Util, 66c Temp, N/A Fan

cmc$ vagrant up
Bringing machine 'default' up with 'aws' provider...
==> default: Warning! The AWS provider doesn't support any of the Vagrant
==> default: high-level network configurations (`config.vm.network`). They
==> default: will be silently ignored.
==> default: Launching an instance with the following settings...
==> default:  -- Type: g2.8xlarge
==> default:  -- AMI: ami-9abea4fb
==> default:  -- Region: us-west-2
==> default:  -- Keypair: cmc_gpucrack
==> default:  -- Security Groups: ["cmc-security-group"]
==> default:  -- Block Device Mapping: []
==> default:  -- Terminate On Shutdown: false
==> default:  -- Monitoring: false
==> default:  -- EBS optimized: false
==> default:  -- Assigning a public IP address in a VPC: false
==> default: Waiting for instance to become "ready"...
==> default: Waiting for SSH to become available...
==> default: Machine is booted and ready for use!
==> default: Rsyncing folder: /Users/cmc/vagrant_aws_gpu/ => /vagrant
==> default: Running provisioner: shell...
