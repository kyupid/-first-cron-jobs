# -first-cron-jobs

Doghoney-site: Crontab.guru  
Doghoney-site2: https://crontab-generator.org/   

Doc source: https://ostechnix.com/a-beginners-guide-to-cron-jobs/

```
Minute(0-59) Hour(0-24) Day_of_month(1-31) Month(1-12) Day_of_week(0-6) Command_to_execute
```
![](https://ostechnix.com/wp-content/uploads/2018/05/cron-job-format-1.png)

To display the contents of the crontab file of the currently logged in user:
```
$ crontab -l
```

To edit the current user's cron jobs, do:
```
$ crontab -e
```

If it is the first time, you will be asked to choose an editor to edit the cron jobs.
```
no crontab for sk - using an empty one

Select an editor. To change later, run 'select-editor'.
 1. /bin/nano <---- easiest
 2. /usr/bin/vim.basic
 3. /usr/bin/vim.tiny
 4. /bin/ed

Choose 1-4 [1]:
```

1. To run a cron job at every minute, the format should be like below.

```
* * * * * <command-to-execute>
```

2. To run cron job at every 5th minute, add the following in your crontab file.

```
*/5 * * * * <command-to-execute>
```

3. To run a cron job at every quarter hour (i.e every 15th minute), add this:
```
*/15 * * * * <command-to-execute>
```

4. To run a cron job every hour at minute 30:
```
30 * * * * <command-to-execute>
```

5. You can also define multiple time intervals separated by commas. For example, the following cron job will run three times every hour, at minute 0, 5 and 10:

```
0,5,10 * * * * <command-to-execute>
```

6. Run a cron job every half hour i.e at every 30th minute:

```
*/30 * * * * <command-to-execute>
```

7. Run a job every hour (at minute 0):

```
0 * * * * <command-to-execute>
```

8. Run a job every 2 hours:

```
0 */2 * * * <command-to-execute>
```

9. Run a job every day (It will run at 00:00):

```
0 0 * * * <command-to-execute>
```

10. Run a job every day at 3am:

```
0 3 * * * <command-to-execute>
```

11. Run a job every Sunday:

```
0 0 * * 0 <command-to-execute>
0 0 * * SUN <command-to-execute>
```

12. Run a job on every day-of-week from Monday through Friday i.e every weekday:

```
0 0 * * 1-5 <command-to-execute>
```

We can also use the following strings to define a cron job.
![image_11](https://user-images.githubusercontent.com/59721293/129821509-fa1fd4b7-7c0d-4be4-ae3d-f5bb7e2125e5.png)

19. To run a job every time the server is rebooted, add this line in your crontab file.

```
@reboot <command-to-execute>
```

20. To remove all cron jobs for the current user:

```
$ crontab -r
```
