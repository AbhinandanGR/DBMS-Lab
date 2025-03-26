<h2>DBMS-Lab</h2>
<p>5<sup>th</sup> Semester Information science and engineering(JSSSTU) DBMS Lab Programs.</p>

program 3
q2)
 select distinct m.mov_title from movies m natural join movie_cast mc where act_id in (select act_id from movie_cast group by act_id having count(distinct mov_id) > 1);
q3)
select distinct act_name from actor natural join movie_cast natural join movies where mov_year not between 2000 and 2015;

q3)
SELECT DISTINCT a.act_id, a.act_name
FROM actor a
JOIN movie_cast mc ON a.act_id = mc.act_id
JOIN movies m ON m.mov_id = mc.mov_id
WHERE m.mov_year < 2000
  AND a.act_id IN (
      SELECT mc1.act_id
      FROM movies m1
      JOIN movie_cast mc1 ON m1.mov_id = mc1.mov_id
      WHERE m1.mov_year > 2020
  );

