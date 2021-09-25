SELECT movie.mov_title, mov_year, mov_dt_rel,
       mov_time,dir_fname, dir_lname 
FROM movie
JOIN  movie_direction 
   ON movie.mov_id = movie_direction.mov_id
JOIN director 
   ON movie_direction.dir_id=director.dir_id
WHERE mov_dt_rel <'01/01/1989'
ORDER BY mov_dt_rel desc;

SELECT mov_title, mov_year, mov_dt_rel, dir_fname, dir_lname, 
       act_fname, act_lname
	   FROM movie a, movie_direction b, director c, 
                rating d, reviewer e, actor f, movie_cast g
	   WHERE a.mov_id=b.mov_id
AND  b.dir_id=c.dir_id 
 AND a.mov_id=d.mov_id 
  AND  d.rev_id=e.rev_id 
   AND  a.mov_id=g.mov_id 
    AND g.act_id=f.act_id 
	 AND e.rev_name IS NULL;


