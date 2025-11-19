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
My project, Service Uptime Checker, is a simple Linux Bash script designed to monitor essential system services like SSH and Apache2. It uses the systemctl command to check whether each service is active and displays a clear message indicating whether the service is running or needs to be restarted. The script demonstrates core shell scripting concepts such as arrays, functions, loops, conditional statements, and exit code checking. It provides an easy way for a system administrator to quickly verify the health status of important services.
