<h1>🌿 NDVI-based Land Cover Classification</h1>
<p>
  This is my submission for <strong>IIT-G CAC's Summer Analytics '25 Kaggle Hackathon</strong>.<br>
  I achieved a public leaderboard score of <strong>0.86247</strong> using Logistic Regression.
</p>

<h2>📄 Problem Statement</h2>
<p>
  The goal was to classify land cover types using NDVI (Normalized Difference Vegetation Index) time-series data.
</p>

<h3>🧠 Key Concepts</h3>
<ul>
  <li><strong>NDVI:</strong> Measures vegetation health using satellite imagery.</li>
</ul>

<h3>⚠️ Data Challenges</h3>
<ul>
  <li><strong>Noise:</strong> Cloud cover and imperfect crowd-sourced labels added significant noise.</li>
  <li><strong>Missing Data:</strong> NDVI values were missing where satellite views were blocked.</li>
  <li><strong>Temporal Variations:</strong> NDVI changes seasonally, so meaningful features had to be extracted carefully.</li>
</ul>

<h3>📦 Dataset Info</h3>
<p>Each row in the dataset includes:</p>
<ul>
  <li><code>class</code>: Land cover type (Water, Impervious, Farm, Forest, Grass, Orchard)</li>
  <li><code>ID</code>: Unique identifier for the sample</li>
  <li><code>27 NDVI Time Points</code>: Columns like <code>20150720_N</code>, <code>20150602_N</code> etc., representing NDVI values across time.</li>
</ul>

<h3>📏 Rules</h3>
<ul>
  <li><strong>Model:</strong> Only Multiclass Logistic Regression was allowed.</li>
  <li><strong>Preprocessing:</strong> Denoising, imputation, and feature engineering were allowed and encouraged.</li>
</ul>

<hr>

<h2>🧠 My Approach</h2>

<h3>🧹 Data Cleaning</h3>
<ul>
  <li>Filled in missing (<code>NaN</code>) values using <strong>backfill (bfill)</strong>.</li>
  <li>For leftover edge values, used the <strong>mean of the column</strong> to impute.</li>
</ul>

<h3>🛠️ Feature Engineering</h3>
<ul>
  <li>Added statistical features like <strong>mean, standard deviation, min, max</strong>, etc.</li>
  <li>Calculated <strong>differences between those features</strong> to highlight temporal patterns.</li>
  <li>Expanded features from <strong>30 → 61</strong>.</li>
</ul>

<h3>🤖 Modeling</h3>
<ul>
  <li>Used a <strong>Multinomial Logistic Regression</strong> model for classification.</li>
  <li>Trained it on the cleaned + engineered dataset and predicted the land cover classes.</li>
</ul>

