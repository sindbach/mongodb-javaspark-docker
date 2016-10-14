mvn exec:java -Dexec.mainClass="tour.JavaIntroduction"

OR 

mvn package 
spark-submit --class tour.JavaIntroduction ./target/tour-1.0-SNAPSHOT.jar 
