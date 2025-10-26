```mermaid
graph LR
    mani_skill_utils_assets_data["mani_skill.utils.assets.data"]
    mani_skill_utils_building_urdf_loader["mani_skill.utils.building.urdf_loader"]
    mani_skill_utils_building__mjcf_loader["mani_skill.utils.building._mjcf_loader"]
    mani_skill_utils_building_actor_builder["mani_skill.utils.building.actor_builder"]
    mani_skill_utils_building_articulation_builder["mani_skill.utils.building.articulation_builder"]
    mani_skill_utils_building_actors_ycb["mani_skill.utils.building.actors.ycb"]
    mani_skill_utils_building_articulations_partnet_mobility["mani_skill.utils.building.articulations.partnet_mobility"]
    mani_skill_envs_scene["mani_skill.envs.scene"]
    mani_skill_utils_building_actors_ycb -- "queries" --> mani_skill_utils_assets_data
    mani_skill_utils_building_articulations_partnet_mobility -- "queries" --> mani_skill_utils_assets_data
    mani_skill_utils_building_articulation_builder -- "consumes output from" --> mani_skill_utils_building_urdf_loader
    mani_skill_utils_building_articulation_builder -- "consumes output from" --> mani_skill_utils_building__mjcf_loader
    mani_skill_utils_building_actors_ycb -- "utilizes" --> mani_skill_utils_building_actor_builder
    mani_skill_utils_building_actor_builder -- "adds to" --> mani_skill_envs_scene
    mani_skill_utils_building_articulations_partnet_mobility -- "leverages" --> mani_skill_utils_building_articulation_builder
    mani_skill_utils_building_articulation_builder -- "adds to" --> mani_skill_envs_scene
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `Asset & Scene Management` subsystem is crucial for defining and populating the simulation environment within the `ManiSkill` framework. It encompasses the loading, parsing, and construction of 3D assets, both rigid and articulated, and their integration into the simulation scene.

### mani_skill.utils.assets.data
Acts as a central registry and provider for asset metadata and file paths, abstracting the storage and retrieval of various asset datasets (e.g., YCB, PartNet-Mobility).


**Related Classes/Methods**:

- <a href="https://github.com/haosulab/ManiSkill/blob/main/mani_skill/utils/assets/data.py" target="_blank" rel="noopener noreferrer">`mani_skill.utils.assets.data`</a>


### mani_skill.utils.building.urdf_loader
Parses URDF (Unified Robot Description Format) files, converting robot and object descriptions into a structured, in-memory format usable by the simulation.


**Related Classes/Methods**:

- <a href="https://github.com/haosulab/ManiSkill/blob/main/mani_skill/utils/building/urdf_loader.py" target="_blank" rel="noopener noreferrer">`mani_skill.utils.building.urdf_loader`</a>


### mani_skill.utils.building._mjcf_loader
Parses MJCF (MuJoCo XML Format) files, similar to URDF, for physical model descriptions, providing an alternative format for asset definition.


**Related Classes/Methods**:

- <a href="https://github.com/haosulab/ManiSkill/blob/main/mani_skill/utils/building/_mjcf_loader.py" target="_blank" rel="noopener noreferrer">`mani_skill.utils.building._mjcf_loader`</a>


### mani_skill.utils.building.actor_builder
Constructs individual rigid body actors (non-articulated objects) within the simulation, handling the creation of visual and collision geometries.


**Related Classes/Methods**:

- <a href="https://github.com/haosulab/ManiSkill/blob/main/mani_skill/utils/building/actor_builder.py" target="_blank" rel="noopener noreferrer">`mani_skill.utils.building.actor_builder`</a>


### mani_skill.utils.building.articulation_builder
Constructs complex articulated models, such as robots, by assembling multiple links and joints based on parsed model data (URDF/MJCF).


**Related Classes/Methods**:

- <a href="https://github.com/haosulab/ManiSkill/blob/main/mani_skill/utils/building/articulation_builder.py" target="_blank" rel="noopener noreferrer">`mani_skill.utils.building.articulation_builder`</a>


### mani_skill.utils.building.actors.ycb
Specializes in integrating objects from the YCB Object and Model Set into the simulation, leveraging `actor_builder` for their construction.


**Related Classes/Methods**:

- <a href="https://github.com/haosulab/ManiSkill/blob/main/mani_skill/utils/building/actors/ycb.py" target="_blank" rel="noopener noreferrer">`mani_skill.utils.building.actors.ycb`</a>


### mani_skill.utils.building.articulations.partnet_mobility
Specializes in integrating articulated models from the PartNet-Mobility dataset, leveraging `articulation_builder` for their complex assembly.


**Related Classes/Methods**:

- <a href="https://github.com/haosulab/ManiSkill/blob/main/mani_skill/utils/building/articulations/partnet_mobility.py" target="_blank" rel="noopener noreferrer">`mani_skill.utils.building.articulations.partnet_mobility`</a>


### mani_skill.envs.scene
Manages the fundamental elements of the simulation scene, including the physics engine, cameras, and lighting, providing the environment where built assets reside and interact.


**Related Classes/Methods**:

- <a href="https://github.com/haosulab/ManiSkill/blob/main/mani_skill/envs/scene.py" target="_blank" rel="noopener noreferrer">`mani_skill.envs.scene`</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)