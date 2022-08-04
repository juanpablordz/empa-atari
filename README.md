# README

This capsule allows the full EMPA2 agent to be run on a specified game and produces a video of the agent's game-play.


### RUNNING THE AGENT

---
Editing the command string in the '/code/run.py' file allows the user to specify the following options:

    python run.py --_game_name='Pong' --_timesteps=30000 --_seed=0 --_tag='demo_v1'

Parameters that can be specified.

    --_game_name [str]: Selects which game to run.
        Options: 'Breakout', 'Pong', 'Carnival', 'SpaceInvaders' and 'Freeway'.
    --_tag [str]: Tag for the experiment.
        Example: 'demo_v1', 'demo_v2', etc...
    --_seed [int]: Seed for the random number generator.
        Example: 42, 31416, etc...
    --_timesteps [int]: Number of timesteps to run the agent for.
        Example: 20000, 30000, etc...



### EXPERIMENT OUTPUT:

---

[NOTE]: Most games take a long time to run -- runs range from 24 to 72 hours.
Time estimates for 25k steps:
    [TODO]
    Breakout: 80 hour ~ 3.5 days
    Pong: 24 hours
    Carnival: 24 hour
    SpaceInvaders: 80 hour ~ 3.5 days
    Freeway: 72 hour ~ 2.5 days


To aid in review, we have prepared demo versions of each game, featuring 5 experiments for each game.

[TODO]: Delete
<!-- While the demo runs, it will produce printouts of when the agent is planning or acting, as well as whether an episode has been won or lost.

Add instructions on where to fin the logs for the experiment that just ran.

    > PATH = "../VGTranspiler/experiments/atari/{game_name}/yyyy.mm.dd/{experiment_id}/{all_experiment_files}" -->

Relevant experiment files:

    - config.txt: Configuration file for the experiment.
    - game_score_{experiment_id}.csv: CSV file containing the game score for each experiment.
    - [TODO] original_movie_{experiment_id}.avi: Original movie of the game.
    - [DEBUG] imgs_movie_{experiment_id}.avi: Movie of the game with the predicted state superimposed.
    <!-- - gamelog_{experiment_id}.log -->



### CODEBASE

---
Code for the EMPA agent is distributed across the following files and directories:

    code/VGTranspiler/

    ENTRY POINT
    -- code/VGTranspiler/run.py: The entrypoint for running the EMPA agent. This file is the only file that needs to be edited to change the game being run.

    AGENT
    -- code/VGTranspiler/EMPA.py: The main file for the EMPA agent.
    -- code/VGTranspiler/hyperparameters.py: This file contains the hyperparameters for the agent.
    -- code/VGTranspiler/perception/:
        | perception_engine.py: The entry point for perception module. Orchestrates mapping from pixels to objects with properties.
    -- code/VGTranspiler/inference/:
        | inference_engine.py: The entry point for inference module. Orchestrates model learning.
        | model_learner.py: The main file for rule learning (Cause -> Effect).
        | property_detector.py: The main file for object class property detection (mass, mask, ..).
        | controller_search.py: The main file for object class controller detection (Walker, Chaser, None).
    -- code/VGTranspiler/planing/:
        | planner.py: The main file for heuristic planning.
        | heuristics/: Contains the heuristics files used by the planner.
    -- code/VGTranspiler/metacontroller/:
        | metacontroller.py: The main file with EMPA's metacontroller functions.
    -- code/VGTranspiler/curiosity/:
        | curiosity.py: This file contains intrinsic curiosity exploration module.

    SIMULATOR
    -- code/VGEngine/: The game engine simulator used by the planner.

    DATA ANALYSIS
    -- code/VGTranspiler/plot/: The plot module.
        | ...



### BASELINES

---
Code for the baselines and ablations has not been reconfigured to run in the capsules, but can be viewed in the following folders/files:

    -- data/baselines/: Contains the baselines for the Deep RL agents and humans.
        | EfficientZero:
        | EfficientRainbow:
        | Random:
        | Human:

    -- data/empa/: Contains EMPA's demo runs.
        | Breakout:
        | Carnival:
        | Freeway:
        | Space Invaders:
        | Pong:




### DATA ANALYSIS

---
For data-analysis code, please see the capsule (directory) titled "Data analysis".

    -- plot/: The plot module.
        |
        |