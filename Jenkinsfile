pipeline {
    agent {
        label 'ubuntuserver'
    }

    stages {
        stage('building') {
            steps {
                sh 'sudo hostnamectl set-hostname "app.kocatepeteknoloji.com"'
                sh 'sudo apt list --upgradable  && sudo apt-get update -y && sudo apt-get upgrade -y'
                sh 'sudo apt install -y lsb-release gnupg2 ca-certificates apt-transport-https software-properties-common'
                sh 'sudo add-apt-repository ppa:ondrej/php'
                sh 'sudo apt install -y nginx php8.1-fpm'
                sh 'sudo apt install -y php8.1-curl php8.1-intl php8.1-dom php8.1-mbstring php8.1-xml php-mysql php-intl php8.1-mysql'
                sh 'sudo apt install mysql-server-8.0 -y'
                sh 'sudo systemctl enable nginx'
                sh 'sudo systemctl start nginx'
                sh 'sudo systemctl enable php8.1-fpm'
                sh 'sudo systemctl start php8.1-fpm'
                sh 'sudo systemctl enable mysql.service'
                sh 'sudo systemctl start mysql.service'
                sh 'sudo mysql -u root -p'
                sh 'sudo mysql -u root -e "CREATE USER \'kocatepeuser\'@\'localhost\' IDENTIFIED BY \'Pa55w0rd\';"'
                sh 'sudo mysql -u root -e "GRANT ALL PRIVILEGES ON kocatepedb.* TO \'kocatepeuser\'@\'localhost\';"'
                sh 'sudo mysql -u root -e "FLUSH PRIVILEGES;"'
                sh 'sudo curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -'
                sh 'sudo apt-get install -y nodejs'
                sh 'sudo apt install composer -y'
                sh 'sudo apt-get update -y && sudo apt-get upgrade -y'

            }
        }
    }
}
