To get SWAGZ going:
1- Install docker: https://lmgtfy.com/?q=install+docker
2- Open a terminal in the root of this folder
3- Type:
	git submodule init
	git submodule update
	docker-compose up

	The first two lines will acknowledge the presence of submodules to the project
	(SBRG's git repos), and the third starts the docker assembly process :)

4- Let the magix happen
5- On your favorite web_browser, navigate to localhost:8910*
6- Enjoy life.



*if you have an old version of Mac OS or MS Windows, you might have had to install
Docker Toolbox instead of Docker for [Mac|Windows]. In that case, docker should tell
you, upon booting, what is the IP of the VM hosting your containers. Go to that IP
instead, which should look like 192.168.*.* (e.g.: 192.168.99.100)

And of course thanks for SBRG, and especially Zachary A. King for his work on the cobra db and BiGG.
This repo is juste a wrapper for all the awesomeness he created.