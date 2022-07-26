# README

This capsule allows the full EMPA2 agent to be run on a specified game, and produces a video of the agent's game-play.

### RUNNING THE AGENT
---
Editing the command string in the 'run' file in /code allows the user to specify the following options:

    python run.py --_game_name='Pong' --_timesteps=30000 --_seed=0 --_tag='demo_v1'

Parameters that can be specified.

    --_game_name [str]: Selects which game to run.
        Options: Breakout, Pong, Carnival, SpaceInvaders and Freeway.
    --_tag [str]: Tag for the experiment.
        Example: demo_v1, demo_v2, etc.
    --_seed [int]: Seed for the random number generator.
    --_timesteps [int]: Number of timesteps to run the agent for.


### EXPERIMENT OUTPUT:
---

[NOTE]: Most games take a long time to run -- runs range from a few minutes to 24 - 72 hours.


To aid in review, we have prepared demo versions of each game. [TODO] ( "demo_mini_aliens", "demo_mini_bait", "demo_mini_butterflies", and "demo_mini_zelda"), featuring only two levels of each game and smaller, simpler game boards on each level.

While the demo runs, it will produce printouts of when the agent is planning or acting, as well as whether an episode has been won or lost.

Add instructions on where to fin the logs for the experiment that just ran.

    > PATH = "../VGTranspiler/experiments/atari/{game_name}/yyyy.mm.dd/{experiment_id}/{all_experiment_files}"

Relevant experiment files:

    - config.txt
    - [DEBUG] imgs_movie_{experiment_id}.avi
    - [TODO] original_movie_{experiment_id}.avi
    - gamelog_{experiment_id}.log
    - game_score_{experiment_id}.csv


### CODEBASE
---
Code for the EMPA agent is distributed across the following files and directories:

[TODO]: Add image of architecture

    ENTRY POINT
    -- run.py: The file that runs the EMPA agent.

    AGENT
    -- hyperparameters.py: The hyperparameters.
    -- EMPA.py: The main file for the EMPA agent.
    -- perception/: The perception module.
        | perception_engine.py: The perception engine.
    -- inference/: The inference module.
        | inference_engine.py: The inference engine.
        | model_learner.py: The model learner.
        | controller_search.py: The controller search module.
    -- planing/: The planing module.
        | planner.py: The planner.
        | heuristics/: The heuristics module.
    -- metacontroller/: The metacontroller module.
        | metacontroller.py: The metacontroller.
    -- curiosity/: The curiosity module.
        | curiosity.py

    SIMULATOR (VGEngine):
    -- VGEngine.py: The VGEngine.


    DATA ANALYSIS
    -- plot/: The plot module.
        | ...


### BASELINES
---
Code for the baselines and ablations has not been reconfigured to run in the capsules, but can be viewed in the following folders/files:

    -- baselines/: The baselines module.
        | Deep RL baselines: /code/DeepRL_Baselines


### DATA ANALYSIS
---
For data-analysis code, please see the capsule (directory) titled "Data analysis".

    -- plot/: The plot module.
        |
        |