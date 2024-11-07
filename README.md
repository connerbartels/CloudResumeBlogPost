# The Cloud Resume Challenge: A Journey Through AWS and Overcoming Struggles

The Cloud Resume Challenge is an exciting project designed to teach cloud computing skills through hands-on experience with AWS services. This project involves creating a personal resume, hosting it on AWS using services like S3, CloudFront, and DynamoDB, and automating deployment with Terraform and GitHub Actions. While the challenge is rewarding in the end, it comes with its fair share of struggles that tested my patience and problem-solving skills.

## Challenges in Hosting the Resume on AWS S3

One of the first hurdles I encountered was hosting my resume on AWS S3 as a static website. S3 is a powerful service, but configuring it correctly for a static website took some time. After uploading the resume’s HTML and CSS, I had to ensure the S3 bucket was configured for public access and static website hosting. The challenge wasn’t so much with the configuration itself, but understanding the specifics of S3 permissions and ensuring the website would load correctly.

After troubleshooting for a while, I was able to configure the S3 bucket settings to work as intended. This taught me the importance of understanding how cloud storage works and how to securely configure resources for web hosting.

## Getting HTTPS to Work with CloudFront

Setting up HTTPS for my resume was another major struggle. Initially, I couldn’t get the SSL certificate working with AWS CloudFront. Without an SSL certificate, the site wouldn’t load over HTTPS, causing security concerns. I had initially struggled with properly linking the SSL certificate from AWS Certificate Manager to my CloudFront distribution. It took multiple attempts to get the right combination of settings in place, and the process was made more difficult by not fully understanding the relationship between CloudFront and S3.

Eventually, after some trial and error, I realized the key was ensuring that both CloudFront and S3 were properly configured to work together with the SSL certificate. This was one of the moments where I had to persist and keep testing until I found the correct solution.

## Route 53 DNS Configuration Problems

One of the most frustrating struggles I faced occurred when configuring DNS settings in Route 53. At one point, I had three different Hosted Zones in Route 53, and it wasn’t clear why my domain wasn’t pointing to the correct resources. This caused issues with my site being inaccessible through HTTPS. I spent hours trying to diagnose the issue, toggling settings in Route 53 and CloudFront, and even considering restarting the whole project out of frustration.

After many attempts, I discovered that the problem was related to misconfigured Hosted Zones and DNS records. By carefully cleaning up the Hosted Zones and ensuring that only the correct one was active, I was able to resolve the issue. This was a tough lesson in the importance of understanding DNS and the impact of multiple configurations that can easily conflict.

## Dealing with the Visitor Counter API

Another challenge was integrating a visitor counter into the resume. The counter was supposed to track the number of visitors to the page and update the count in AWS DynamoDB. At first, the counter was updating correctly on the AWS side, but the JavaScript code wouldn’t trigger the API Gateway to update the count. I spent hours troubleshooting the code, checking both the front-end and back-end components. It was incredibly frustrating to see the counter work intermittently, even though everything seemed set up properly.

The breakthrough came when I realized that the issue was related to the permissions and CORS configuration in the API Gateway. Once I updated the settings to properly allow requests from my S3-hosted resume domain, the counter worked as expected. This experience reinforced how important it is to carefully configure the back-end components, especially when dealing with APIs and security settings.

## Terraform: Overcoming Initial Struggles

One of the most daunting aspects of this challenge was learning Terraform and using it to automate the infrastructure deployment. Initially, I had no experience with Terraform, and I struggled to understand how to write the configuration files to define and deploy resources in AWS. I spent several hours trying to figure out how to initialize and apply Terraform configurations, and I was almost ready to give up.

Thankfully, I found some useful tutorials and documentation online, which helped me understand how to structure the files and use the `terraform apply` command to deploy resources. I learned that Terraform's ability to automate cloud resource management is a game-changer, and while the learning curve was steep, it was ultimately one of the most rewarding aspects of the project. This experience taught me the importance of automation and how powerful infrastructure as code can be.

## CI/CD Pipelines and GitHub Actions

Setting up CI/CD pipelines with GitHub Actions was another challenge, but it was also one of the most useful learning experiences. I had to set up two separate workflows: one for deploying Python Lambda code and another for deploying the Terraform infrastructure. The challenge here was ensuring that each workflow triggered the correct steps, ran the necessary tests, and deployed changes automatically when code was pushed to the repository.

It took several tries to get the workflows working perfectly. The syntax for GitHub Actions was initially confusing, and I had to read through many tutorials to fully understand how to configure the YAML files for each action. Once everything clicked, the CI/CD setup became a time-saver, and I realized the power of automation in streamlining deployments. This part of the project taught me the importance of CI/CD in modern software development and how it can improve efficiency and reduce the chances of human error.

## Conclusion: Overcoming Obstacles and Gaining Valuable Skills

Despite the struggles, completing the Cloud Resume Challenge was incredibly rewarding. Each obstacle forced me to learn something new, and overcoming them helped solidify my understanding of cloud computing, serverless architecture, and infrastructure as code. From working with AWS services like S3, CloudFront, and Lambda to configuring CI/CD pipelines with Terraform and GitHub Actions, I gained valuable hands-on experience that will be crucial for my future career in cloud computing.

While there were moments of frustration, the process of solving these problems was a significant learning experience. The challenge helped me develop not only technical skills but also problem-solving and persistence. These are the kinds of lessons that can’t be taught in a textbook—they come from rolling up your sleeves and pushing through challenges until you find the solution.
