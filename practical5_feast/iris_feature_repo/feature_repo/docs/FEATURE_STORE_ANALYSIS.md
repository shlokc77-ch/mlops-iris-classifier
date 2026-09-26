# Feature Store Analysis

## 1. Elimination of Training-Serving Skew

Feast provides a centralized definition of the Iris features through
FeatureViews in `features.py`.

The same registered feature definitions are used for both historical
feature retrieval and online feature retrieval. This reduces the risk of
different feature-engineering logic being used during training and
inference.

In this practical, the same engineered features such as `sepal_area`,
`petal_area`, and `sepal_to_petal_length_ratio` were retrieved through
both the offline and online paths.

## 2. Feature Reusability

The features were defined once in Feast and registered through the
`iris_feature_service` Feature Service.

The same registered features were then reused by another consumer through
the Feature Service without implementing the feature calculations again.

This reduces duplicated feature-engineering work and improves consistency
between different ML tasks.

## 3. Centralized Governance

The `features.py` file provides a central definition of the entity,
feature source, FeatureViews, schemas, TTLs, and Feature Service.

This creates a single source of truth for the features used by the
different consumers of the feature store.

## 4. Offline and Online Feature Retrieval

The online store is used for retrieving current feature values for an
entity, while historical retrieval is used to construct training data
using event timestamps.

In this practical, both retrieval paths successfully returned the Iris
features.

## 5. Point-in-Time Correctness

Historical retrieval uses the event timestamp associated with each entity
row. This allows Feast to retrieve feature values corresponding to the
appropriate point in time and helps prevent future-information leakage
during training-data construction.