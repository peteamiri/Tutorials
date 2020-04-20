# AWS Certification – Application Services – Cheat Sheet

## SQS

*   extremely scalable queue service and potentially handles millions of messages
*   helps build fault tolerant, distributed loosely coupled applications
*   **stores copies of the messages on multiple servers** for redundancy and high availability
*   guarantees **At-Least-Once Delivery**, but does not guarantee Exact One Time Delivery which might result in **duplicate** messages (<span style="color: #ff0000;">Not true anymore with the introduction of FIFO queues</span>)
*   **does not maintain or guarantee message order**, and if needed sequencing information needs to be added to the message itself (<span style="color: #ff0000;">Not true anymore with the introduction of FIFO queues</span>)
*   **supports multiple readers and writers** interacting with the same queue as the same time
*   holds message for 4 days, by default, and can be changed from 1 min – 14 days after which the message is deleted
*   message needs to be **explicitly deleted** by the consumer once processed
*   allows send, receive and delete **batching** which helps club up to 10 messages in a single batch while charging price for a single message
*   handles visibility of the message to multiple consumers using **Visibility Timeout**, where the message once read by a consumer is not visible to the other consumers till the timeout occurs
*   can handle load and performance requirements by scaling the worker instances as the demand changes (**Job Observer pattern**)
*   message sample allowing **short and long polling**
    *   returns immediately **<span style="color: #ff0000;">vs</span>** waits for fixed time for e.g. 20 secs
    *   might not return all messages as it samples a subset of servers **<span style="color: #ff0000;">vs</span>** returns all available messages
    *   repetitive **<span style="color: #ff0000;">vs</span>** helps save cost with long connection
*   supports **delay queues** to make messages available after a certain delay, can you used to differentiate from priority queues
*   supports **dead letter queues**, to redirect messages which failed to process after certain attempts instead of being processed repeatedly
*   **Design Patterns**
    *   **Job Observer Pattern** can help coordinate number of EC2 instances with number of job requests (Queue Size) automatically thus Improving cost effectiveness and performance
    *   **Priority Queue Pattern** can be used to setup different queues with different handling either by delayed queues or low scaling capacity for handling messages in lower priority queues

## SNS

*   delivery or sending of messages to subscribing endpoints or clients
*   **publisher-subscriber** model
*   Producers and Consumers communicate **asynchronously** with subscribers by producing and sending a message to a topic
*   supports **Email (plain or JSON), HTTP/HTTPS, SMS, SQS**
*   supports **Mobile Push Notifications** to push notifications directly to mobile devices with services like Amazon Device Messaging (ADM), Apple Push Notification Service (APNS), Google Cloud Messaging (GCM) etc. supported
*   **order is not guaranteed** and **No recall** available
*   **integrated with Lambda** to invoke functions on notifications
*   **for Email notifications, use SNS or SES directly, SQS does not work**

## SWF

*   **orchestration service** to coordinate work across distributed components
*   helps define tasks, stores, assigns tasks to workers, define logic, tracks and monitors the task and maintains workflow state in a durable fashion
*   helps define tasks which can be executed on AWS cloud or **on-premises**
*   helps coordinating tasks across the application which involves managing intertask dependencies, scheduling, and concurrency in accordance with the logical flow of the application
*   supports **built-in retries, timeouts and logging**
*   supports **manual tasks**
*   Characteristics
    *   deliver exactly once
    *   uses long polling, which reduces number of polls without results
    *   Visibility of task state via API
    *   Timers, signals, markers, child workflows
    *   supports versioning
    *   keeps workflow history for a user-specified time
*   AWS SWF vs AWS SQS
    *   task-oriented <span style="color: #ff0000;">**vs**</span> message-oriented
    *   track of all tasks and events <span style="color: #ff0000;">**vs**</span> needs custom handling

## SES

*   highly scalable and cost-effective email service
*   uses **content filtering technologies** to scan outgoing emails to check standards and email content for spam and malware
*   **supports full fledged emails to be sent as compared to SNS where only the message is sent in Email**
*   ideal for **sending bulk emails** at scale<span id="ezoic-pub-ad-placeholder-122" class="ezoic-adpicker-ad"></span><span style="display:block !important;float:none;margin-bottom:20px !important;margin-left:0px !important;margin-right:0px !important;margin-top:10px !important;min-height:60px;min-width:468px;text-align:center !important;" class="ezoic-ad box-4 adtester-container adtester-container-122" data-ez-name="jayendrapatil_com-box-4"><span id="div-gpt-ad-jayendrapatil_com-box-4-0" ezaw="468" ezah="60" style="position:relative;z-index:0;display:inline-block;min-height:60px;min-width:468px;" class="ezoic-ad"><script data-ezscrex="false" data-cfasync="false" type="text/javascript" style="display:none;">eval(ez_write_tag([[468,60],'jayendrapatil_com-box-4','ezslot_3',122,'0','0']));</script></span></span>
*   **guarantees first hop**
*   eliminates the need to support custom software or applications to do heavy lifting of email transport
