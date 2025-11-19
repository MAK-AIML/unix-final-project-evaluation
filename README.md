# unix-final-project-evaluation

#!/bin/bash            

# List of services to check
SERVICES=("ssh" "apache2") 

check_service() {                                        
    local service="$1"                                    
    systemctl is-active --quiet "$service" 
    if [ $? -eq 0 ]; then       
        echo "Checking $service service... Running"
    else
        echo "Checking $service service... Not Running (Restart Required)"
    fi   
}

for s in "${SERVICES[@]}"; do        
    check_service "$s"      
done
This project is a simple Linux automation script that checks whether important system services, such as SSH and Apache2, are running. It uses the systemctl command to verify the status of each service and displays a message indicating whether it is currently active. If a service is not running, the script alerts the user that a restart may be required. The project demonstrates the use of Bash scripting concepts such as arrays, functions, loops, exit codes ($?), and conditional statements to create a basic monitoring tool suitable for system administration tasks.
