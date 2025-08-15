1. Create Network ```docker network create -d bridge lab-net```.
2. Deploy [Kali](https://hub.docker.com/r/kalilinux/kali-rolling).
    1. Download image ```docker image pull kalilinux/kali-rolling```.
    2. Run container ```docker run --name attacker --network lab-net -it -d kalilinux/kali-rolling:latest```.
    3. Update packages and install tools ```apt update && apt -y install kali-linux-headless```. Configure some packages during setup.
    4. Install ```iputils-ping``` and ping target.
3. Deploy [Juice Shop](https://hub.docker.com/r/bkimminich/juice-shop/).
    1. Download image ```docker image pull bkimminich/juice-shop```.
    2. Run container ```docker run --name attacker --network lab-net -it -d bkimminich/juice-shop:latest```.
<img width="1254" height="1031" alt="image" src="https://github.com/user-attachments/assets/622115d0-c2ea-44b7-afaf-bcfc6bd26bf8" />
<img width="896" height="242" alt="image" src="https://github.com/user-attachments/assets/a94c6ac2-8390-4aba-9386-90ad4575b2d9" />
