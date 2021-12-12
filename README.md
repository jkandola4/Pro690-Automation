# Pro690-Automation
Devops Automation pro690

To start off our automation process, you will be doing all of the code using windows Terminal, you can also use command prompt and powershell. Make sure its in administrator mode.

Key items to note anything inside the brackets (...) is the code and command to type in you can copy and paste the code and it will work, remove () for it to work.

Install minikube

Start off the install minikube by going to https://minikube.sigs.k8s.io/docs/start/ and Download minikube and install.
Start the process by typing (minikube start) to start the installation of kubernetes and prepare docker.

Install Kubectl
Go to this link and install kubectl by clicking 1. Download the lastest release from here 
https://kubernetes.io/docs/tasks/tools/install-kubectl-windows/
Verify the installation by typing (kubectl cluster-info)

Important step for kube ctl
You have to make a new folder in C drive like C:\Kube and put in the exe in there. 
Go to search bar and type in edit enviornment variables. edit path and add the location of kube so c:\Kube.

Configuring minikube

Type this command in to add more ram to Kubernetes (minikube config -p kubevirt set memory 4096)

Install kubevirt operator
In terminals type in (wget https://github.com/kubevirt/kubevirt/releases/download/v0.48.0/kubevirt-operator.yaml) to install kubevirt
After to apply the download type in (kubectl apply -f kubevirt-operator.yaml)
Next is enabling software emulation type in (kubectl create configmap kubevirt-config -n kubevirt --from-literal debug-useEmulation=true)

Kubevirt 
Type in (wget https://github.com/kubevirt/kubevirt/releases/download/v0.48.0/kubevirt-cr.yaml) to download it
apply the yaml by typing (kubectl apply -f kubevirt-cr.yaml)
Check if it is working by typing (kubectl get pods -n kubevirt)

Deploying The Virtual Machine
Type in (kubectl apply -f vm.yaml) to start the machine
to get the status of the machine type (kubectl get vm)

To get into the virtual machine, you can start off by opening Oracle Box Virtual machine and open the Minikube Virtual machine. 
This is where would login into the command line interface. Once you have done this you have Completed Our Devops Automation, You can now install the applications that you would like that require reliability and redundancy. As this is built straight into the virtual machine. No other configuration is required to start the redundancy etc. Install the program and let it run and never experience downtime

Login for Virtual Machine
username: docker
password: tcuser

Compile of all code used in this process.

minikube start
kubectl cluster-info
minikube config -p kubevirt set memory 4096
wget https://github.com/kubevirt/kubevirt/releases/download/v0.48.0/kubevirt-operator.yaml
kubectl apply -f kubevirt-operator.yaml
kubectl create configmap kubevirt-config -n kubevirt --from-literal debug-useEmulation=true
wget https://github.com/kubevirt/kubevirt/releases/download/v0.48.0/kubevirt-cr.yaml
kubectl apply -f kubevirt-cr.yaml
kubectl get pods -n kubevirt
kubectl apply -f vm.yaml
kubectl get vm

