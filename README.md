# MagicalRealism
Summer Literature Course
echo "# MagicalRealism" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/nmkostiw/MagicalRealism.git
git push -u origin master

CREATE (himym:TVShow {name: "How I Met Your Mother"})
CREATE (himym_s1:Season {name: "HIMYM Season 1"})
CREATE (himym_s1_e1:Episode {name: "Pilot"})
CREATE (ted:Character {name: "Ted Mosby"})
CREATE (joshRadnor:Actor {name: "Josh Radnor"})
CREATE UNIQUE (joshRadnor)-[:PLAYED_CHARACTER]->(ted)
CREATE UNIQUE (himym)-[:HAS_SEASON]->(himym_s1)
CREATE UNIQUE (himym_s1)-[:HAS_EPISODE]->(himym_s1_e1)
CREATE UNIQUE (himym_s1_e1)-[:FEATURED_CHARACTER]->(ted)
CREATE (himym_s1_e1_review1 {title: "Meet Me At The Bar In 15 Minutes & Suit Up", content: "It was awesome"})
CREATE (wakenPayne:User {name: "WakenPayne"})
CREATE (wakenPayne)-[:WROTE_REVIEW]->(himym_s1_e1_review1)<-[:HAS_REVIEW]-(himym_s1_e1)
