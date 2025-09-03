apt update
apt install -y curl
curl -fsSL https://deb.nodesource.com/setup_18.x | bash -
apt install -y nodejs
git clone https://github.com/snyk-labs/nodejs-goof.git
cd nodejs-goof
git remote remove origin
git remote add origin https://github.com/Tsunami281/8.2CDevSecOps.git
git push -u origin main

