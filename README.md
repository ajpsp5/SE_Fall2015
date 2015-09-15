<h1>Tenative Database</h1>
<hr>
<br>
<br>
<h2>Queries</h2>
<hr>
<h4>Tickets are produced and prepared to be sold to the public.</h4>
<tb><code>select * from tickets;</code>
<tb><p>Shows all tickets available</p>
<br>
<h4>The competing athletes are notified of the time and place for their competition.</h4>
<tb><p>Check what competition the athlete attends</p>
<tb><code>select g.name as 'Competition', g.id as 'Competition_id', g.time, g.location_name  from athletegamerelationship agr
inner join athletes a on agr.athlete = a.id
inner join games g on agr.game = g.id
where a.id = {Athlete ID};
</code>

