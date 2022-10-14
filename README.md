# Customer Clustering

1)	**Database Files:** all the data is in the database.zip
2)	**Download Script:** Customer_Segmentation.zip

**CASE GOAL:** Segment customers based on different clustering methods and strategies.

- **DBSCAN** (Density-based clustering method)
    - Min. samples and Epsilon parameters defined using two
    - methodologies (K-NN and K-MEANS)
    - **Notebooks:** _Customer_Segmentation_DBSCAN_VF3_6M-Filter.ipynb_ and _Customer_Segmentation_DBSCAN_VF3_12M-Filter.ipynb_
    
- **K-MEANS** (Distance-based clustering method)
    - **Notebook:** _Customer_Segmentation_K_Means.ipynb_

- **HIERARQUICAL CLUSTERING**
    - Agglomerative nesting (bottom-up)
    - Builds a hierarchy of clusters
    - **Notebook:** _Customer_Segmentation_Hierarchical Clustering.ipynb_

## Experimental Setup and Algorithms

1) FEATURE SELECTION
2) LEARNING
3) EVALUATION

![experimental](https://user-images.githubusercontent.com/95027395/183254199-a9b46f94-613b-4ed5-a1f1-0e9714ad6703.PNG)

### 1.1 Feature Selection: RFM Model

RFM = (Recency, Frequency, Monetary) Analysis
  - Effective customer segmentation technique with extensive literature
  - Very helpful for marketers to make strategic choices in business

Selected features for the RFM model:
- Recency: days_since_last_buy
- Frequency: num_orders
- Monetary Value: product_net_amount_sum

![RFM](https://user-images.githubusercontent.com/95027395/183254721-360b00d3-59a7-4177-981e-d2b87a5420de.PNG)


### 1.2 Feature Selection: selecting features after analysis and testing

- Manual selection based on relevance to the business and feature correlation
- Sixteen features were selected based on their relevance to the business goal and with this work:

1. num_orders 9. product_qty_ordered_trend
2. num_orders_60d 10. order_shipping_price_trend
3. num_orders_90d 11. free_shipping_sum
4. product_total_amount_trend 12. free_shipping_pct
5. product_total_amount_sum 13. with_discount_sum
6. product_total_discount_trend 14. with_discount_pct
7. product_net_amount_trend 15. number_brands_sum
8. product_net_amount_sum 16. Number_sku_sum
9. product_qty_ordered_trend
10. order_shipping_price_trend
11. free_shipping_sum
12. free_shipping_pct
13. with_discount_sum
14. with_discount_pct
15. number_brands_sum
16. Number_sku_sum

![feature selection](blob:https://web.whatsapp.com/d2316248-6964-4cc9-8f65-0587ad28b032)


### Evaluation of the learning process

Silhouette (SL) and Davies-Bouldin (DB) scores were used to evaluate the several clustering techniques. The K-means algorithm using the RFM selected features using a 6-month period got the best performance for both scores.

![evaluation](https://user-images.githubusercontent.com/95027395/183254935-5d37a16c-287a-464d-be68-d5606d4154f5.PNG)


## Output

#### **Best Silhouette Score** = 0.167
#### **Best Davies-Bouldin Score** = 1.502

### Main Takeways:
- Cluster 2 (purple) is the best costumer and should be retained.

- Clusters 0 (green) and 1 (red) have similar behavior, with Cluster 3 having bought a
higher basket value. Regardless of this value, both clusters only buy once and a long
time ago.

- Cluster 3 (blue) should be the main focus of Care to Beauty. All these clients are very
recent and must be nurtured so that they can be converted on a Cluster 2 type and
not a 0 or 1 type.

![types](https://user-images.githubusercontent.com/95027395/183255146-c075ba42-c702-4ee7-adce-a480e9c5e984.PNG)

### Snake Plot

![Snake plot](https://user-images.githubusercontent.com/95027395/183255153-66c807ff-3aba-4e5b-a6ce-b3ad467d4bd5.PNG)

### 3D Plot

![3D Plot](https://user-images.githubusercontent.com/95027395/183255175-8d530dc9-e591-49a7-a947-9218a631bc99.PNG)

### 2D Plot

![2D flatted](https://user-images.githubusercontent.com/95027395/183255180-f08b8d26-23c1-4b24-9b08-cb2be76a00a4.PNG)


## Statistics

![Statistics](https://user-images.githubusercontent.com/95027395/183255202-4c1c9908-4a02-4e0c-9691-1d380ca4cce9.PNG)
