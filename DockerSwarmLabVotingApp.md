Access the voting-app code at 
https://github.com/dockersamples/example-voting-app

## on Master Node :

	$yum install docker
	$service docker  start
	$docker swarm init --advertise-addr $(hostname -i)

Download the code

	$yum install git -y
	$git clone https://github.com/docker/example-voting-app

	$cd example-voting-app
	$cat docker-stack.yml

Deploy the stack 

	$docker stack deploy --compose-file=docker-stack.yml voting_stack
	$docker stack ls

For each services do ---

	$docker stack services voting_stack
	$docker service ps voting_stack_vote

scale a service:
	
	$docker service scale voting_stack_vote=5

	$docker service ls

	$docker service update --replicas 2 voting_stack_vote

	$docker service update --replicas 2 voting_stack_redis
  
## On Worker Node:

	$yum install docker

	$service docker  start

	$docker swarm join --token SWMTKN-1-3gs4q4rqygek2dalg3adauucjgqem3d6058yzwwt7rq6kugl01-1s0r6qevn4idfy87nmy11lhvj 192.168.0.28:2377



##########################
To create swarm using Hyper V container
https://www.cardinalsolutions.com/blog/2017/06/docker_swarm_mode_part_1

