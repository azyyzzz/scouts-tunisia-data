%%{ init: { 'themeVariables': { 'primaryColor': '#ffcc00', 'edgeColor': '#425a81', 'tertiaryColor': '#eaeaea' }}}%%
classDiagram
    direction TB

    class FAIT_ACTIVITES {
        +activity_id
        +activity_name
        +date_id
        +location_id
        +season_id
    }

    class FAIT_MEMBRES {
        +member_id
        +member_name
        +age_group_id
    }

    class FAIT_BUDGET {
        +budget_id
        +amount
        +date_id
    }

    class FAIT_SPONSORS {
        +sponsor_id
        +sponsor_name
    }

    class FAIT_CAMPS {
        +camp_id
        +camp_name
        +location_id
    }

    class FAIT_PARTICIPATION_LEADERS {
        +participation_id
        +leader_id
        +activity_id
    }

    class DIM_DATE {
        +date_id
        +date
    }

    class DIM_SAISON {
        +season_id
        +season_name
    }

    class DIM_UNITE {
        +unit_id
        +unit_name
    }

    class DIM_TRANCHE_AGE {
        +age_group_id
        +age_range
    }

    class DIM_TYPE_ACTIVITE {
        +activity_type_id
        +activity_type_name
    }

    class DIM_LIEU {
        +location_id
        +location_name
    }

    FAIT_ACTIVITES --> DIM_DATE : uses
    FAIT_ACTIVITES --> DIM_UNITE : uses
    FAIT_ACTIVITES --> DIM_SAISON : uses
    FAIT_MEMBRES --> DIM_TRANCHE_AGE : uses
    FAIT_MEMBRES --> DIM_DATE : uses
    FAIT_BUDGET --> DIM_DATE : uses

    FAIT_SPONSORS --> FAIT_ACTIVITES : sponsored in
    FAIT_CAMPS --> FAIT_ACTIVITES : hosted in
    FAIT_PARTICIPATION_LEADERS --> FAIT_ACTIVITES : involves
