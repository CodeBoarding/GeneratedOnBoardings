```mermaid
graph LR
    User_Interface_UI_Module["User Interface (UI) Module"]
    Groove_Data_Model_Manager["Groove Data Model & Manager"]
    Audio_Playback_Engine["Audio Playback Engine"]
    Notation_Rendering_Engine["Notation Rendering Engine"]
    Persistence_Manager["Persistence Manager"]
    Practice_Tools_Module["Practice Tools Module"]
    User_Interface_UI_Module -- "sends user input to" --> Groove_Data_Model_Manager
    Groove_Data_Model_Manager -- "sends updated groove data to" --> User_Interface_UI_Module
    User_Interface_UI_Module -- "sends playback commands to" --> Audio_Playback_Engine
    Audio_Playback_Engine -- "sends playback status updates to" --> User_Interface_UI_Module
    Groove_Data_Model_Manager -- "sends musical data to" --> Notation_Rendering_Engine
    Notation_Rendering_Engine -- "sends rendered notation to" --> User_Interface_UI_Module
    User_Interface_UI_Module -- "sends save/load requests to" --> Persistence_Manager
    Groove_Data_Model_Manager -- "sends groove data for saving to" --> Persistence_Manager
    Persistence_Manager -- "provides loaded groove data to" --> Groove_Data_Model_Manager
    User_Interface_UI_Module -- "sends practice feature input to" --> Practice_Tools_Module
    Practice_Tools_Module -- "sends playback control commands to" --> Audio_Playback_Engine
    Practice_Tools_Module -- "sends practice feedback to" --> User_Interface_UI_Module
    click User_Interface_UI_Module href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/GrooveScribe/User_Interface_UI_Module.md" "Details"
    click Groove_Data_Model_Manager href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/GrooveScribe/Groove_Data_Model_Manager.md" "Details"
    click Audio_Playback_Engine href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/GrooveScribe/Audio_Playback_Engine.md" "Details"
    click Notation_Rendering_Engine href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/GrooveScribe/Notation_Rendering_Engine.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The GrooveScribe application is architected as a single-page web application with a strong client-side focus. The User Interface (UI) Module serves as the primary interaction point, driven by the GrooveWriter class which acts as a central controller. This controller directly manages the Groove Data Model & Manager, handling the creation, modification, and storage of musical grooves. It also orchestrates interactions with the Audio Playback Engine for sound generation and the Notation Rendering Engine for visual display of sheet music. The Persistence Manager handles data saving and loading, primarily through local storage, while the Practice Tools Module provides specialized functionalities for learning and practicing. This design promotes a cohesive and interactive user experience, with js/groove_writer.js being the pivotal file integrating most of the application's core logic.

### User Interface (UI) Module [[Expand]](./User_Interface_UI_Module.md)
The presentation layer, responsible for rendering all visual elements, handling user input, and displaying application state. It acts as the primary interface for user interaction.


**Related Classes/Methods**:

- `GrooveWriter`
- `GrooveUtils`
- `GrooveDBCreateGroove.html`
- `GrooveEmbed.html`
- `GrooveMultiDisplay.html`
- `GScribeMusicImageOnly.html`
- `InterestingGrooves.html`
- `TestAllTimeSigs.html`
- `WeirdTimeSigsTest.html`


### Groove Data Model & Manager [[Expand]](./Groove_Data_Model_Manager.md)
The core data layer, defining, storing, and managing the structure and content of musical "grooves." It acts as the central repository for all musical data, including notes, time signatures, and other musical properties.


**Related Classes/Methods**:

- `GrooveWriter`
- `GrooveUtils`
- `grooves`


### Audio Playback Engine [[Expand]](./Audio_Playback_Engine.md)
Manages all audio-related functionalities, including MIDI playback, sound synthesis, and synchronization with musical notation, leveraging the HTML5 Audio API and external MIDI.js library.


**Related Classes/Methods**:

- `GrooveWriter.play_single_note_for_note_setting`
- `MIDI`
- `MIDI`
- `MIDI`
- `MIDI`


### Notation Rendering Engine [[Expand]](./Notation_Rendering_Engine.md)
Dedicated to processing musical data from the Groove Data Model and rendering it into a visual sheet music format, primarily using SVG for scalable display.


**Related Classes/Methods**:

- `GrooveWriter.refresh_ABC`
- `GrooveWriter.displayNewSVG`
- `abc2svg-1.js`


### Persistence Manager
Handles the saving and loading of groove data to and from the client's local storage, ensuring data persistence across browser sessions.


**Related Classes/Methods**:

- `GrooveWriter.saveABCtoFile`
- `GrooveWriter.getQueryVariableFromURL`


### Practice Tools Module
Encapsulates the logic for practice-specific features, such as looping sections, adjusting playback speed, and metronome functions, designed to aid users in learning and practicing musical grooves.


**Related Classes/Methods**:

- `GrooveWriter.metronomeButtonClick`
- `GrooveWriter.changeDivision`
- `GrooveWriter.toggleAdvancedEdit`




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)