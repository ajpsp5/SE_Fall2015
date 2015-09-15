<h1>Tenative Database</h1>
<hr>
<br>
<br>
<h2>Queries</h2>
<hr>

<h4>Tickets are produced and prepared to be sold to the public.</h4>
<tb><p>- Shows all tickets available</p>
<tb><code>select * from tickets;</code>

<br>
<h4>The competing athletes are notified of the time and place for their competition.</h4>
<p>- Check what competition the athlete attends</p>
<code>select g.name as 'Competition', g.id as 'Competition_id', g.time, g.location_name  from athletegamerelationship agr
inner join athletes a on agr.athlete = a.id
inner join games g on agr.game = g.id
where a.id = {Athlete ID};
</code>
<p>- Save Notification from the above query</p>
<code>insert into notifications (message, type)values('Your Event {Event Name} is at {Event Time & Date} in {Event Location}', 'R');</code>
<p>"R" means Reminder</p>
<p>- Save Game Notification Relationship</p>
<code>insert into gamenotificationsrelationship (game, notification) values({Game ID}, {Notification ID});</code>
<br>

<h4>The Security department is notified to provide security guards and the necessary security equipment.</h4>
<tb><p>- Create Message for Security</p>
<tb><code>insert into notifications (message, type)values('Security Guards are needed at {Event Name}', 'S');</code>
<p>"S" means Security</p>
<p>- Save Game Notification Relationship</p>
<code>insert into gamenotificationsrelationship (game, notification, securityMessage) values({Game ID}, {Notification ID}, 'Y');</code>
<br>

<h4>The medals ceremonies are scheduled.</h4>
<tb><p>- Get all scheduled ceremonies</p>
<tb><code>select * from ceremonies where date(date)>=date(NOW());</code>

<br>
<hr>
<br>

<h3>Q/A</h3>
<h4>The Security department is notified to provide security guards and the necessary security equipment.</h4>
<tb><p>- Create Message for Security</p>
<tb><code>insert into notifications (message, type)values('Security Guards are needed at {Event Name}', 'S');</code>
<p>"S" means Security</p>
