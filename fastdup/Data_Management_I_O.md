```mermaid
graph LR
    Dataset_Manager["Dataset Manager"]
    Image_I_O_Processing_Core["Image I/O & Processing Core"]
    Dataset_Manager -- "delegates image operations to" --> Image_I_O_Processing_Core
    Image_I_O_Processing_Core -- "provides image handling services to" --> Dataset_Manager
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `fastdup` image processing subsystem is primarily composed of two key components: the `Dataset Manager` and the `Image I/O & Processing Core`. The `Dataset Manager` serves as the high-level orchestrator, responsible for managing image datasets, including data ingestion, metadata handling, and saving processed files. It delegates all low-level image reading, writing, and basic manipulation tasks to the `Image I/O & Processing Core`. In turn, the `Image I/O & Processing Core` provides robust and efficient services for handling individual image data, abstracting away complexities of various storage backends and offering essential image processing utilities. This architectural design ensures a clear separation of concerns, allowing for scalable and maintainable image data processing workflows.

### Dataset Manager
This component is responsible for the high-level orchestration of image datasets. It handles the initial data ingestion by scanning specified directories, managing the generation and caching of dataset metadata, and overseeing the process of saving processed image files. It acts as the primary interface for dataset-level operations, crucial for a data analysis library preparing inputs for ML models.


**Related Classes/Methods**:

- <a href="https://github.com/visual-layer/fastdup/blob/main/fastdup/datasets.py#L123-L129" target="_blank" rel="noopener noreferrer">`scan_dir`:123-129</a>
- <a href="https://github.com/visual-layer/fastdup/blob/main/fastdup/datasets.py#L120-L133" target="_blank" rel="noopener noreferrer">`_generate_img_folder_hash`:120-133</a>
- <a href="https://github.com/visual-layer/fastdup/blob/main/fastdup/datasets.py#L144-L153" target="_blank" rel="noopener noreferrer">`_retrieve_cached_metadata`:144-153</a>
- <a href="https://github.com/visual-layer/fastdup/blob/main/fastdup/datasets.py#L135-L142" target="_blank" rel="noopener noreferrer">`_cache_metadata`:135-142</a>
- <a href="https://github.com/visual-layer/fastdup/blob/main/fastdup/datasets.py#L184-L192" target="_blank" rel="noopener noreferrer">`_save_as_image_files`:184-192</a>
- <a href="https://github.com/visual-layer/fastdup/blob/main/fastdup/datasets.py#L155-L182" target="_blank" rel="noopener noreferrer">`_save_single_image`:155-182</a>


### Image I/O & Processing Core
This component provides the fundamental, low-level capabilities for handling individual image data. It abstracts away the complexities of reading images from various sources (local, S3, MinIO), ensures valid image writing, and offers a suite of basic image manipulation utilities. This core functionality is essential for any computer vision or ML toolkit.


**Related Classes/Methods**:

- <a href="https://github.com/visual-layer/fastdup/blob/main/fastdup/image.py#L143-L219" target="_blank" rel="noopener noreferrer">`fastdup_imread`:143-219</a>
- <a href="https://github.com/visual-layer/fastdup/blob/main/fastdup/image.py#L102-L105" target="_blank" rel="noopener noreferrer">`download_s3`:102-105</a>
- <a href="https://github.com/visual-layer/fastdup/blob/main/fastdup/image.py#L93-L100" target="_blank" rel="noopener noreferrer">`download_minio`:93-100</a>
- <a href="https://github.com/visual-layer/fastdup/blob/main/fastdup/image.py#L118-L141" target="_blank" rel="noopener noreferrer">`inner_read`:118-141</a>
- <a href="https://github.com/visual-layer/fastdup/blob/main/fastdup/image.py#L228-L255" target="_blank" rel="noopener noreferrer">`fastdup_imwrite`:228-255</a>
- <a href="https://github.com/visual-layer/fastdup/blob/main/fastdup/image.py#L222-L225" target="_blank" rel="noopener noreferrer">`check_valid_image_extension`:222-225</a>
- <a href="https://github.com/visual-layer/fastdup/blob/main/fastdup/image.py#L357-L439" target="_blank" rel="noopener noreferrer">`create_triplet_img`:357-439</a>
- <a href="https://github.com/visual-layer/fastdup/blob/main/fastdup/image.py#L334-L355" target="_blank" rel="noopener noreferrer">`draw_text`:334-355</a>
- <a href="https://github.com/visual-layer/fastdup/blob/main/fastdup/image.py#L293-L297" target="_blank" rel="noopener noreferrer">`hconcat_resize_min`:293-297</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)