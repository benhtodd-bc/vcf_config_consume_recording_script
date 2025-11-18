# vcf_config_consume_recording_script

## Lab 3 vSphere Supervisor Activation
as a Day-2 Operations



tar xvf ~/Downloads/vcf-cli.tar.gz
sudo mv ~/Downloads/vcf-cli-linux_amd64 /usr/local/bin/vcf

VMware1!

vcf version

echo 'source <(vcf completion bash)' >> ~/.bash_profile
source ~/.bash_profile


cd ~/Downloads
curl -LO https://dl.k8s.io/release/v1.33.0/bin/linux/amd64/kubectl
ls -l kubectl
sudo chmod +x kubectl
ls -l kubectl
sudo mv kubectl /usr/local/bin/
alias k='kubectl'
kubectl version
kubectl --help
echo 'source <(kubectl completion bash)' >> ~/.bash_profile
source ~/.bash_profile


vcf context create --endpoint=<Kubernetes API Server IP> --insecure-skip-tls-verify