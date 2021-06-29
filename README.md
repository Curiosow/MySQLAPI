# MySQLAPI
# This is a API for use MySQL easily in your project.
# Creator: PauLeK

# for use it:

Download the jar, put in the plugin folder AND in the build path

# So, for first, we connect to the database, put that in the main class (don't forget to modify the Strings)

    private PluginDescriptionFile pdf;
    public MySQL SQL;
    public boolean connected;
    public String HOST = "YOUR HOST";
    public String DATABASE = "YOUR DATABASE";
    public String USER = "YOUR USER";
    public String PASS = "YOUR PASS";
    
# Now, we will does the connexion, put that in the onEnable()

    this.pdf = this.getDescription();
		
		this.SQL = new MySQL((Main) this.getServer().getPluginManager().getPlugin("MySQL"), pdf.getName());
        this.connected = SQL.Connect(HOST, DATABASE, USER, PASS);
       
        if(!this.connected) {
            this.getLogger().info("The connexion to the MySQL Database has failed.");
        }
# Now, the connexion is ready, for first, we will execute a MySQL command (don't forget to place the real name of your main class)

    YOURMAIN.getInstance().SQL.update("HERE, PUT YOUR MYSQL COMMAND");

# And, if you want a data, it's a little more difficult but, you can understand. I've create a method, it's better

    public static void getMyInformation(String info) {
    
      static String sInformation;
    
	  	String qInformation = String.format("YOUR MYSQL LINE FOR GET THE INFORMATION");
		  ResultSet set = YOURMAIN.getInstance().SQL.query(qInformation);
		  try {
		  	while (set.next()) {
			  	sInformation = set.getString("info");
		  	}
		  } catch (SQLException e) {
			  test.getInstance().getLogger().info("Error executing query:");
			  test.getInstance().getLogger().info(qInformation);
	      }
  	}
  # I know, it's not easy to understand so, add me on Discord for ask me the problem/question (Curiosow ፨ Oscar#1963)
