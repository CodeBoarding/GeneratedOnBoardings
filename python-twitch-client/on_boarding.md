```mermaid
graph LR
    Twitch_API_Clients["Twitch API Clients"]
    API_Request_Handling["API Request Handling"]
    Twitch_Data_Models["Twitch Data Models"]
    API_Configuration_Utilities["API Configuration & Utilities"]
    Old_API_Specific_Endpoints["Old API Specific Endpoints"]
    Twitch_API_Clients -- "uses" --> API_Configuration_Utilities
    Twitch_API_Clients -- "delegates to" --> Old_API_Specific_Endpoints
    Twitch_API_Clients -- "uses" --> API_Request_Handling
    API_Request_Handling -- "uses" --> API_Configuration_Utilities
    API_Request_Handling -- "produces" --> Twitch_Data_Models
    Twitch_Data_Models -- "consumed by" --> Twitch_API_Clients
    Twitch_Data_Models -- "consumed by" --> Old_API_Specific_Endpoints
    API_Configuration_Utilities -- "used by" --> Twitch_API_Clients
    API_Configuration_Utilities -- "used by" --> API_Request_Handling
    Old_API_Specific_Endpoints -- "uses" --> API_Request_Handling
    Old_API_Specific_Endpoints -- "produces" --> Twitch_Data_Models
    Old_API_Specific_Endpoints -- "uses" --> API_Configuration_Utilities
    click Twitch_API_Clients href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/python-twitch-client/Twitch API Clients.md" "Details"
    click API_Request_Handling href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/python-twitch-client/API Request Handling.md" "Details"
    click Twitch_Data_Models href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/python-twitch-client/Twitch Data Models.md" "Details"
    click API_Configuration_Utilities href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/python-twitch-client/API Configuration & Utilities.md" "Details"
    click Old_API_Specific_Endpoints href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/python-twitch-client/Old API Specific Endpoints.md" "Details"
```
[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Component Details

This graph illustrates the architecture of the `python-twitch-client` library, which provides a comprehensive interface for interacting with both the older Twitch API (v5) and the newer Twitch Helix API. The core functionality revolves around making API requests, handling responses by converting them into Python objects, and managing authentication and configuration.

### Twitch API Clients
Provides the main interfaces for interacting with both the older Twitch API (v5) and the newer Twitch Helix API, acting as a facade for different API versions and their respective functionalities.


**Related Classes/Methods**:

- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/client.py#L24-L43" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.client.TwitchClient:__init__` (24:43)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/client.py#L46-L51" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.client.TwitchClient:channel_feed` (46:51)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/client.py#L54-L59" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.client.TwitchClient:clips` (54:59)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/client.py#L62-L67" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.client.TwitchClient:channels` (62:67)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/client.py#L70-L73" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.client.TwitchClient:chat` (70:73)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/client.py#L76-L81" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.client.TwitchClient:collections` (76:81)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/client.py#L84-L89" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.client.TwitchClient:communities` (84:89)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/client.py#L92-L97" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.client.TwitchClient:games` (92:97)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/client.py#L100-L105" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.client.TwitchClient:ingests` (100:105)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/client.py#L108-L113" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.client.TwitchClient:search` (108:113)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/client.py#L116-L121" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.client.TwitchClient:streams` (116:121)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/client.py#L124-L129" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.client.TwitchClient:teams` (124:129)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/client.py#L132-L137" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.client.TwitchClient:users` (132:137)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/client.py#L140-L145" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.client.TwitchClient:videos` (140:145)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/helix/api.py#L32-L41" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.helix.api.TwitchHelix:__init__` (32:41)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/helix/api.py#L43-L70" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.helix.api.TwitchHelix:get_oauth` (43:70)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/helix/api.py#L72-L118" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.helix.api.TwitchHelix:get_streams` (72:118)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/helix/api.py#L120-L136" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.helix.api.TwitchHelix:get_games` (120:136)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/helix/api.py#L138-L187" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.helix.api.TwitchHelix:get_clips` (138:187)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/helix/api.py#L189-L205" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.helix.api.TwitchHelix:get_top_games` (189:205)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/helix/api.py#L207-L271" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.helix.api.TwitchHelix:get_videos` (207:271)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/helix/api.py#L273-L319" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.helix.api.TwitchHelix:get_streams_metadata` (273:319)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/helix/api.py#L321-L340" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.helix.api.TwitchHelix:get_user_follows` (321:340)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/helix/api.py#L342-L358" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.helix.api.TwitchHelix:get_users` (342:358)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/helix/api.py#L360-L376" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.helix.api.TwitchHelix:get_tags` (360:376)</a>


### API Request Handling
Manages the underlying HTTP communication with both Twitch API v5 and Helix endpoints, including handling request headers, rate limits, and pagination for efficient data retrieval.


**Related Classes/Methods**:

- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/api/base.py#L15-L20" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.api.base.TwitchAPI:__init__` (15:20)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/api/base.py#L22-L32" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.api.base.TwitchAPI:_get_request_headers` (22:32)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/api/base.py#L34-L57" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.api.base.TwitchAPI:_request_get` (34:57)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/api/base.py#L59-L70" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.api.base.TwitchAPI:_request_post` (59:70)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/api/base.py#L72-L82" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.api.base.TwitchAPI:_request_put` (72:82)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/api/base.py#L84-L95" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.api.base.TwitchAPI:_request_delete` (84:95)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/helix/base.py#L18-L38" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.helix.base.TwitchAPIMixin:_wait_for_rate_limit_reset` (18:38)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/helix/base.py#L40-L46" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.helix.base.TwitchAPIMixin:_get_request_headers` (40:46)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/helix/base.py#L48-L76" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.helix.base.TwitchAPIMixin:_request_get` (48:76)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/helix/base.py#L80-L95" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.helix.base.APICursor:__init__` (80:95)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/helix/base.py#L118-L133" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.helix.base.APICursor:next_page` (118:133)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/helix/base.py#L140-L143" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.helix.base.APICursor:total` (140:143)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/helix/base.py#L155-L157" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.helix.base.APIGet:fetch` (155:157)</a>


### Twitch Data Models
Defines the Python object structures for representing various Twitch API resources, facilitating the conversion of raw API responses into easily manipulable objects within the application.


**Related Classes/Methods**:

- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/resources.py#L4-L34" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.resources:convert_to_twitch_object` (4:34)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/resources.py#L58-L61" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.resources.TwitchObject:construct_from` (58:61)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/resources.py#L63-L65" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.resources.TwitchObject:refresh_from` (63:65)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/resources.py#L53-L55" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.resources.TwitchObject.__setitem__` (53:55)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/resources.py#L81-L82" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.resources.Channel` (81:82)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/resources.py#L85-L86" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.resources.Clip` (85:86)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/resources.py#L89-L90" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.resources.Collection` (89:90)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/resources.py#L93-L94" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.resources.Comment` (93:94)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/resources.py#L97-L98" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.resources.Community` (97:98)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/resources.py#L101-L102" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.resources.Featured` (101:102)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/resources.py#L105-L106" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.resources.Follow` (105:106)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/resources.py#L109-L110" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.resources.Game` (109:110)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/resources.py#L113-L114" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.resources.Ingest` (113:114)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/resources.py#L117-L118" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.resources.Item` (117:118)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/resources.py#L121-L122" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.resources.Post` (121:122)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/resources.py#L125-L126" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.resources.Stream` (125:126)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/resources.py#L129-L130" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.resources.StreamMetadata` (129:130)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/resources.py#L133-L134" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.resources.Subscription` (133:134)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/resources.py#L137-L138" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.resources.Tag` (137:138)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/resources.py#L141-L142" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.resources.Team` (141:142)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/resources.py#L145-L146" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.resources.TopGame` (145:146)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/resources.py#L149-L150" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.resources.User` (149:150)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/resources.py#L153-L154" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.resources.UserBlock` (153:154)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/resources.py#L157-L158" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.resources.Video` (157:158)</a>


### API Configuration & Utilities
Handles the loading and management of API credentials and settings, provides custom exception handling for API-related errors, and enforces authentication requirements for sensitive operations.


**Related Classes/Methods**:

- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/conf.py#L13-L22" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.conf:credentials_from_config_file` (13:22)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/conf.py#L25-L34" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.conf:backoff_config` (25:34)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/conf.py#L7-L10" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.conf._get_config` (7:10)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/exceptions.py#L1-L2" target="_blank" rel="noopener noreferrer">`twitch.exceptions.TwitchException` (1:2)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/exceptions.py#L5-L6" target="_blank" rel="noopener noreferrer">`twitch.exceptions.TwitchAuthException` (5:6)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/exceptions.py#L9-L10" target="_blank" rel="noopener noreferrer">`twitch.exceptions.TwitchAttributeException` (9:10)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/exceptions.py#L13-L14" target="_blank" rel="noopener noreferrer">`twitch.exceptions.TwitchNotProvidedException` (13:14)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/exceptions.py#L17-L18" target="_blank" rel="noopener noreferrer">`twitch.exceptions.TwitchOAuthException` (17:18)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/decorators.py#L4-L10" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.decorators.oauth_required` (4:10)</a>


### Old API Specific Endpoints
Encapsulates the specific functionalities and methods for interacting with various categories of the older Twitch API (v5), such as channels, streams, users, and communities.


**Related Classes/Methods**:

- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/api/collections.py#L8-L10" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.api.collections.Collections:get_metadata` (8:10)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/api/collections.py#L12-L17" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.api.collections.Collections:get` (12:17)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/api/collections.py#L19-L31" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.api.collections.Collections:get_by_channel` (19:31)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/api/collections.py#L34-L41" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.api.collections.Collections:create` (34:41)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/api/collections.py#L44-L48" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.api.collections.Collections:update` (44:48)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/api/collections.py#L51-L55" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.api.collections.Collections:create_thumbnail` (51:55)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/api/collections.py#L58-L59" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.api.collections.Collections:delete` (58:59)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/api/collections.py#L62-L67" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.api.collections.Collections:add_item` (62:67)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/api/collections.py#L70-L72" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.api.collections.Collections:delete_item` (70:72)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/api/collections.py#L75-L78" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.api.collections.Collections:move_item` (75:78)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/api/streams.py#L8-L83" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.api.streams.Streams` (8:83)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/api/users.py#L14-L130" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.api.users.Users` (14:130)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/api/chat.py#L4-L18" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.api.chat.Chat` (4:18)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/api/communities.py#L7-L136" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.api.communities.Communities` (7:136)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/api/channel_feed.py#L7-L105" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.api.channel_feed.ChannelFeed` (7:105)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/api/teams.py#L6-L19" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.api.teams.Teams` (6:19)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/api/videos.py#L14-L88" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.api.videos.Videos` (14:88)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/api/games.py#L6-L15" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.api.games.Games` (6:15)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/api/channels.py#L16-L156" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.api.channels.Channels` (16:156)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/api/clips.py#L8-L56" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.api.clips.Clips` (8:56)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/api/ingests.py#L5-L8" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.api.ingests.Ingests` (5:8)</a>
- <a href="https://github.com/tsifrer/python-twitch-client/blob/master/twitch/api/search.py#L6-L33" target="_blank" rel="noopener noreferrer">`python-twitch-client.twitch.api.search.Search` (6:33)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)