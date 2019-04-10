PROJET : FEU DE SIGNALISATION AVEC L’INTERFACE GRAPHIQUE

Présente par : Samba bailo ba

Ce projet consiste à effectuer une simulation des feux de signalisation en utilisant java swing. 

Explication du code :
Création des boutons run et stop
JButton start; 
    JButton stop; 
    Boolean i;
Création d’un constructeur
    //create constructor method 
    public Feu_Signalisation(String title) { 
Création du bouton start
      // create Start button 
      start = new JButton("Start"); 
Création du bouton stop
      //create Stop button 
      stop = new JButton("Stop");
Enregistrer des actions listeners 
      //add Action listeners 
      start.addActionListener(this); 
      stop.addActionListener(this); 
Création d’un Panel bouton
      //create new Button Panel 
      JPanel buttonPanel = new JPanel(); 
      buttonPanel.add(start); 
      buttonPanel.add(stop); 
      Container c = getContentPane(); 
      c.add(buttonPanel, BorderLayout.SOUTH); 

      setSize(200, 425); 
      setLocationRelativeTo(null); 
      setResizable(false); 
      setVisible(true); 
      setDefaultCloseOperation(EXIT_ON_CLOSE); 
    } 
La méthode run permet de démarrer un feu et de faire dormir les autres.Pour cela on s’est sur la notion de sémaphore avec les processus (thread).
public void run(){ 
        while(i) { 
          try{ 
            red(g); 
            if(!i) { 
              break; 
            } 
            Thread.sleep(1000); 
            amber(g); 
            if(!i) { 
              break; 
            } 
            Thread.sleep(1000); 
            green(g); 
            if(!i){ 
              break; 
            } 
            Thread.sleep(1000); 


          }catch(InterruptedException e) { 
             e.printStackTrace(); 
         } 
        } 
      }  
Exécution



