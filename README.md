# magandata

magandata aspires to unlock the inherent beauty concealed within datasets, empowering analysts and scientists to 
effortlessly craft and manipulate tidy analytic data in R.

## Dataset De-Identification and Re-Identification with Key Dictionary

The process of de-identifying or re-identifying a dataset is streamlined with the utilization of the `key_dictionary.R` 
module, which uses two functions:

1. **`attach_surrogate_id()`**
2. **`attach_original_id()`**

### Key Dictionary Creation

Before proceeding with de-identification or re-identification, a key dictionary is established. If one already exists, 
it is referenced; otherwise, a new key dictionary is created. The columns generated in this process are:

- `key_category`: This parameter, customizable by the user, signifies the type of key being created. The default is set 
to `Patient`, but users can specify an alternative category.
- `source_key`: Represents the original keys in the dataset.
- `surrogate_key`: Contains the surrogate keys generated by the key dictionary.
- `created_dttm`: Indicates the date and time each row in the key dictionary was created.

### De-Identification Process - `attach_surrogate_id()`

The `attach_surrogate_id()` function introduces a unique and random surrogate key column to all identifiers in the 
dataset, aligning with the specified key category. Users have the flexibility to decide whether to retain or remove the 
original identifier by setting the parameter `keep_original_key_column` to `TRUE` or `FALSE`. Both the original 
identifier and its corresponding surrogate key for each row are cataloged in the key dictionary for future reference.

### Re-Identification Process - `attach_original_id()`

Conversely, the `attach_original_id()` function invokes the key dictionary to reintroduce the unique identifier back 
into a dataset containing the matching surrogate key and the designated key category. Users can decide whether to keep 
or remove the surrogate key by adjusting the `keep_surrogate_key_column` parameter. This feature enables a seamless 
restoration of the original identifiers, facilitating a reversible process when necessary.

Enhance your dataset management workflow by efficiently de-identifying and re-identifying data with the powerful and 
user-friendly `key_dictionary.R` module.
