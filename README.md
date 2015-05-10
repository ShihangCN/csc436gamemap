# csc436gamemap
The some code about add the game information
Scanner scan = new Scanner(new File("map.txt"));
ArrayList<String> lines = new ArrayList<String>();
while(scan.hasNextLine()) {
   lines.add(scan.nextLine());
}
scan.close();

MapObject objects[][] = new MapObject[lines.size()][lines.get(0).length()];

for(int a = 0; a < lines.size(); a++) {
   for(int b = 0; b < lines.get(a).length(); b++) {
      char c = lines.get(a).charAt(b);
      
      if(c == 'E') objects[a][b] = new Enemy(a,b);
      if(c == 'P') objects[a][b] = new Platform(a,b);
      if(c == 'H') objects[a][b] = new Hero(a,b);
   }
}
