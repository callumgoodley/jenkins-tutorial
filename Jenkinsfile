pipeline{
        agent any
        stages{
            stage('Clone repo'){
                steps{
                    sh "sudo apt install git-all
                        git clone https://gitlab.com/qacdevops/chaperootodo_client.git"
                }
            }
            stage('Install docker and docker-compose'){
                steps{
                    sh "sudo apt update 
sudo apt install -y curl jq
curl https://get.docker.com | sudo bash
version=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | jq -r '.tag_name')
sudo curl -L "https://github.com/docker/compose/releases/download/${version}/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose"
                }
             }
             stage('build'){
                steps{
                    sh "sudo docker-compose up -d"
                            }
                          } 
        }    
}
