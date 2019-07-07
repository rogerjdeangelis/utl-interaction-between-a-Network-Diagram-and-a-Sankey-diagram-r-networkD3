# utl-interaction-between-a-Network-Diagram-and-a-Sankey-diagram-r-networkD3
Interaction between a Network Diagram and a Sankey diagram

    Interaction between a Network Diagram and a Sankey diagram                                                                          
                                                                                                                                        
    github (webshot of output)                                                                                                          
    https://tinyurl.com/yyawnpp5                                                                                                        
    https://github.com/rogerjdeangelis/utl-interaction-between-a-Network-Diagram-and-a-Sankey-diagram-r-networkD3/blob/master/netSan.png
                                                                                                                                        
    github                                                                                                                              
    https://tinyurl.com/y5qrtu8s                                                                                                        
    https://github.com/rogerjdeangelis/utl-interaction-between-a-Network-Diagram-and-a-Sankey-diagram-r-networkD3                       
                                                                                                                                        
    SAS Forum                                                                                                                           
    https://communities.sas.com/t5/New-SAS-User/Create-relationship-between-Network-Diagram-and-Sankey-diagram/m-p/571649               
                                                                                                                                        
    Doc                                                                                                                                 
    https://www.r-graph-gallery.com/323-sankey-diagram-with-the-networkd3-library/                                                      
                                                                                                                                        
    You need to instal phatomjs web browser and phantomjs to windows path                                                               
                                                                                                                                        
    To view the diagram created you have to download the zip file and extract to a folder.                                              
    I extracted into d:/htm                                                                                                             
                                                                                                                                        
    You will get a directory                                                                                                            
                                                                                                                                        
         d:/htm/netSan_files    ** directory                                                                                            
         d:/htm/netscan.html    ** click on this to get hi ri-res output                                                                
                                                                                                                                        
    *_                   _                                                                                                              
    (_)_ __  _ __  _   _| |_                                                                                                            
    | | '_ \| '_ \| | | | __|                                                                                                           
    | | | | | |_) | |_| | |_                                                                                                            
    |_|_| |_| .__/ \__,_|\__|                                                                                                           
            |_|                                                                                                                         
    ;                                                                                                                                   
    options validvarname=upcase;                                                                                                        
    libname sd1 "d:/sd1";                                                                                                               
                                                                                                                                        
    data sd1.nodes;                                                                                                                     
       input source target value @@;                                                                                                    
    cards4;                                                                                                                             
    0 1 124.729 1 2 0.597 1 3 26.862 1 4 280.322 1 5 81.144 6 2 35 7                                                                    
    4 35 8 9 11.606 10 9 63.965 9 4 75.571 11 12 10.639 11 13 22.505                                                                    
    11 14 46.184 15 16 104.453 15 14 113.726 15 17 27.14 15 12                                                                          
    342.165 15 18 37.797 15 19 4.412 15 13 40.858 15 3 56.691 15 20                                                                     
    7.863 15 21 90.008 15 22 93.494 23 24 40.719 25 24 82.233 5 13                                                                      
    0.129 5 3 1.401 5 26 151.891 5 19 2.096 5 12 48.58 27 15 7.013                                                                      
    17 28 20.897 17 3 6.242 28 18 20.897 29 15 6.995 2 12 121.066 2                                                                     
    30 128.69 2 18 135.835 2 31 14.458 2 32 206.267 2 19 3.64 2 33                                                                      
    33.218 2 20 4.413 34 1 4.375 24 5 122.952 35 26 839.978 36 37                                                                       
    504.287 38 37 107.703 37 2 611.99 39 4 56.587 39 1 77.81 40 14                                                                      
    193.026 40 13 70.672 41 15 59.901 42 14 19.263 43 42 19.263 43                                                                      
    41 59.901 4 19 0.882 4 26 400.12 4 12 46.477 26 15 525.531 26 3                                                                     
    787.129 26 11 79.329 44 15 9.452 45 1 182.01 46 15 19.013 47 15                                                                     
    289.366                                                                                                                             
    ;;;;                                                                                                                                
    run;quit;                                                                                                                           
                                                                                                                                        
                                                                                                                                        
    data sd1.links;                                                                                                                     
     infile cards4 dsd delimiter='@';                                                                                                   
     length name $44;                                                                                                                   
     input name @@;                                                                                                                     
    cards4;                                                                                                                             
    Agricultural 'waste'@Bio-conversion@Liquid@Losses@Solid@Gas@Biofuel imports                                                         
    Biomass imports@Coal imports@Coal@Coal reserves@District heating@Industry                                                           
    Heating and cooling - commercial@Heating and cooling - homes@Electricity grid                                                       
    Over generation / exports@H2 conversion@Road transport@Agriculture                                                                  
    Rail transport@Lighting & appliances - commercial@Lighting & appliances - homes                                                     
    Gas imports@Ngas@Gas reserves@Thermal generation@Geothermal@H2@Hydro                                                                
    International shipping@Domestic aviation@International aviation                                                                     
    National navigation@Marine algae@Nuclear@Oil imports@Oil@Oil reserves                                                               
    Other waste@Pumped heat@Solar PV@Solar Thermal@Solar@Tidal                                                                          
    UK land based bioenergy@Wave@Wind                                                                                                   
    ;;;;                                                                                                                                
    run;quit;                                                                                                                           
                                                                                                                                        
                                                                                                                                        
    SD1.NODES total obs=68                                                                                                              
                                                                                                                                        
      SOURCE    TARGET      VALUE                                                                                                       
                                                                                                                                        
         0         1      124.729                                                                                                       
         1         2        0.597                                                                                                       
         1         3       26.862                                                                                                       
         1         4      280.322                                                                                                       
         1         5       81.144                                                                                                       
         6         2       35.000                                                                                                       
         7         4       35.000                                                                                                       
         8         9       11.606                                                                                                       
        10         9       63.965                                                                                                       
         9         4       75.571                                                                                                       
        11        12       10.639                                                                                                       
        11        13       22.505                                                                                                       
      ...                                                                                                                               
                                                                                                                                        
    SD1.LINKS total obs=48                                                                                                              
                                                                                                                                        
      NAME                                                                                                                              
                                                                                                                                        
      Agricultural 'waste'                                                                                                              
      Bio-conversion                                                                                                                    
      Liquid                                                                                                                            
      Losses                                                                                                                            
      Solid                                                                                                                             
      Gas                                                                                                                               
      Biofuel imports                                                                                                                   
      Biomass imports                                                                                                                   
      Coal imports                                                                                                                      
      Coal                                                                                                                              
      ....                                                                                                                              
                                                                                                                                        
    *            _               _                                                                                                      
      ___  _   _| |_ _ __  _   _| |_                                                                                                    
     / _ \| | | | __| '_ \| | | | __|                                                                                                   
    | (_) | |_| | |_| |_) | |_| | |_                                                                                                    
     \___/ \__,_|\__| .__/ \__,_|\__|                                                                                                   
                    |_|                                                                                                                 
    ;                                                                                                                                   
                                                                                                                                        
     https://tinyurl.com/yyawnpp5                                                                                                       
                                                                                                                                        
                                                                                                                                        
    *          _       _   _                                                                                                            
     ___  ___ | |_   _| |_(_) ___  _ __                                                                                                 
    / __|/ _ \| | | | | __| |/ _ \| '_ \                                                                                                
    \__ \ (_) | | |_| | |_| | (_) | | | |                                                                                               
    |___/\___/|_|\__,_|\__|_|\___/|_| |_|                                                                                               
                                                                                                                                        
    ;                                                                                                                                   
                                                                                                                                        
    %utlfkil(d:/htm/netscan.html); * not really needed - code will replace it;                                                          
                                                                                                                                        
    %utl_submit_r64('                                                                                                                   
    library(networkD3);                                                                                                                 
    library(SASxport);                                                                                                                  
    library(htmlwidgets);                                                                                                               
    library(data.table);                                                                                                                
    library(rbokeh);                                                                                                                    
    library(haven);                                                                                                                     
    library(dplyr);                                                                                                                     
    nodes<-read_sas("d:/sd1/nodes.sas7bdat");                                                                                           
    links<-read_sas("d:/sd1/links.sas7bdat");                                                                                           
    Energy <- list(nodes,links);                                                                                                        
    htmgph<-sankeyNetwork(Links = Energy[[1]], Nodes = Energy[[2]], Source = "SOURCE",                                                  
        Target = "TARGET", Value = "VALUE", NodeID = "NAME",                                                                            
        units = "TWh", fontSize = 12, nodeWidth = 30);                                                                                  
    saveWidget(htmgph, "d:/htm/netSan.html", selfcontained = FALSE);                                                                    
    ');                                                                                                                                 
                                                                                                                                        
                                                                                                                                        
                                                                                                                                        
