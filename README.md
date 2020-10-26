# HelloWorld-EEG

Build version alpha 0.04

Author: Joseph O'Neill


Tool usage:

  - To build a deep NN
  
  - To test the accuracy of the model in predicting timeseries multivariate classification


Data:

  - EEG recordings from an EMOTIV EPOC+
  
  - EEG recording and file conversion from edf to csv with EMOTIV PRO software
  
  - EEG recordings in two sets of subvocalized words: hello, world


Neural Network:
  - Conv. RNN based on the paper:

      Cascade and Parallel Conv. NN on EEG-based Intention Recogn for BCI by Lina Yao et al.

  - As of this build haven't decided on Cascade or Parallel
  
  - I am leaning towards trying the Cascade CRNN but it is still early


Current usage abilities:
  
  - Loads in all the csv files with glob

  - ! EACH MAP IS MAPPED TO ITS CORRESPONDING ORIGINAL FILE NAME !

  - maps the files by word (hello vs world) into 2 dictionaries or file maps

        > (hello_file_map, world_file_map)

  - Converts the file maps from array into meshes and maps into mesh maps
        
        > (hello_mesh_map, world_mesh_map)
  
  - Takes the mesh mapping and uses the z-score standardization

    as instructed in the paper -> working towards Cascade CRNN
    
  - Saves Z standard meshes into a new Z_map

        > (hello_z_map, world_z_map)

### Added in Version a0.04

  - Functions to simplify z_score_converion function

        > (mesh_mean(), mesh_sigma(), mesh_z())
