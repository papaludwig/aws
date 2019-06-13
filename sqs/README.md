# Build and Consume Simple Queue Service (SQS) Queues Using Browser Console

# Creating queues and sending messages
1. Navigate to Services | SQS
2. Click the Create New Queue button.
3. Investigate the two major kinds of queues: Standard and FIFO.
4. Click "Configure Queue"and investigate SQS Queue Options. Leave all values at defaults.
5. Enter a name of [UserName]-queue1, be sure "Standard Queue" is chosen and click Quick-Create-Queue
6. Find the newly created queue in the dashboard. Click on it.
7. Examine the "Details" tab, notice some of the options.
8. Right-click your queue in the dashboard list and choose Send a Message
9. Type a message body of "This is message 1" and click the Send Message button.
11. Click Send Another Message when informed that the message was sent to the queue.
12. Change the message body to "This is message 2" and click the Send Message button.
13. Repeat the previous two steps three more times for message bodies of "... message 3", "... message 4", and "... message 5".
14. Click the Close button to stop sending messages
15. Right-click your queuein the dashboard list and choose View/Delete Messages
16. Click "Start Polling for Messages"
   - Were the messages received in the same order in which they were added?
   - Remember, after being received, messages are invisible for the Message Visibility Timeout. This timeout defaults to 30 seconds.
17. Click "Stop Now" and wait for polling tp stop
18. Click "Start Polling for Messages" again.
   - Were the messages received in the same order in which they were added? Where they receieved in the same order as the first polling?
19. Click "Stop Now"
20. Click "Close"
21. Click the "Permissions" tab for your queue.
22. Click "Add a Permission"
23. Experiment with the various available permissions.
24. Click the Cancel link in the Add a Permission dialog
25. Right--click your queue and choose "Delete Queue"
26. If prompted about messages remainin, click "Yes, Delete Queue"
