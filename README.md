# spring-jndi-lookup
How to lookup data source from JNDI using spring 

# Server.xml

<Resource name="jdbc/javatechie" 
      global="jdbc/javatechie" 
      auth="Container" 
      type="javax.sql.DataSource" 
      driverClassName="com.mysql.jdbc.Driver" 
      url="jdbc:mysql://localhost:3306/javatechie" 
      username="root" 
      password="Password" 
      
      maxActive="100" 
      maxIdle="20" 
      minIdle="5" 
      maxWait="10000"/>
	  
# context.xml:	  

<ResourceLink name="jdbc/javatechie"
                	global="jdbc/javatechie"
                    auth="Container"
                    type="javax.sql.DataSource" />
					
# Config:

<jee:jndi-lookup id="dataSource" jndi-name="jdbc/javatechie"
   			expected-type="javax.sql.DataSource" />					
					
