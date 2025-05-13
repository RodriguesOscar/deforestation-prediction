# Literature Review

Approaches or solutions that have been tried before on similar projects.

**Summary of Each Work**:

- **Source 1**: Using Random Forest to model deforestation risk in the Amazon rainforest  
  - **[Link](https://doi.org/10.1016/j.ecolmodel.2006.03.003)**  
  - **Objective**: To simulate and predict deforestation trends in the Amazon using data-driven spatial modeling.  
  - **Methods**: Employed Random Forest models trained on spatial predictors including distance to roads, land use, population density, and protection status of areas.  
  - **Outcomes**: Achieved high predictive performance and highlighted the importance of infrastructure proximity and land use pressure in deforestation dynamics.  
  - **Relation to the Project**: Reinforces the relevance of Random Forest for spatial prediction tasks and informs the selection of critical features for modeling deforestation risk in Amazonas.

- **Source 2**: Modelagem da dinâmica do desmatamento na Amazônia Legal  
  - **[Link](http://mtc-m16b.sid.inpe.br/col/sid.inpe.br/mtc-m17@80/2007/05.09.14.53/doc/SBGFA_Ari.PDF)**  
  - **Objective**: To investigate spatial patterns of deforestation across the Brazilian Amazon and support environmental policy design.  
  - **Methods**: Combined GIS-based spatial analysis with environmental and socioeconomic variables such as road networks, protected areas, and deforestation records.  
  - **Outcomes**: Produced a risk map of deforestation and supported government decision-making regarding conservation priorities and resource allocation.  
  - **Relation to the Project**: Validates the importance of spatial features and demonstrates how predictive modeling can support strategic environmental planning in Amazonas.

- **Source 3**: MapBiomas Project – Annual Land Use and Land Cover Mapping  
  - **[Link](https://mapbiomas.org)**  
  - **Objective**: To produce annual, high-resolution maps of land use and land cover across Brazil for environmental monitoring.  
  - **Methods**: Utilized machine learning models on Landsat satellite imagery, supported by human validation and institutional collaboration.  
  - **Outcomes**: Generated a reliable, longitudinal dataset that captures the dynamics of forest loss and land conversion.  
  - **Relation to the Project**: Serves as a key data source for training and validating deforestation prediction models, especially for feature engineering related to land use transitions.


**Conclusion**  
The reviewed literature confirms that spatial modeling using environmental and anthropogenic factors is a well-established approach to predict deforestation in the Amazon. The work by Soares-Filho et al. (2006) shows that Random Forest is an effective model for identifying high-risk zones based on features like roads, land use, and protected areas. The study "Modelagem da dinâmica do desmatamento na Amazônia Legal" reinforces this by using official data from the Brazilian Amazon to guide spatial predictions aligned with government monitoring objectives. Lastly, the MapBiomas project stands out as a reliable source of annual land use and land cover data, which is frequently used as a feature in deforestation models. These insights confirm the suitability of Random Forest and logistic regression for this type of classification problem, and they guide the selection of features for building a predictive model focused on the state of Amazonas.
