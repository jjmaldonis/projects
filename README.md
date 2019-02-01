# My Projects

This is a collection of some of my more interesting projects. I rarely work by myself so my projects are often collaborations and are housed under various other organizations. All projects are currently written in Python.


### mpi4py Examples

During my graduate work I developed some code (StructOpt, see below) that made extensive use of `mpi4py`. `mpi4py` is a Python wrapper for MPI software, which allows for communication between many nodes in a high-performance cluster. In order to test the MPI environment, I developed a few examples related to splitting the MPI communicator and spawning child processes through MPI. I put these examples on github with a bit of documentation. To my surprise, the repository has a few stars. The number of `mpi4py` users is small in comparison to the larger academic computing field, so even a few stars suggests that my examples are useful to others.


### Cassiopeia

https://github.com/meraki-analytics/cassiopeia

Cassiopeia (aka Cass) is a python wrapper for the Riot Games API with unparalleled features. Cass collects and manages data about the game League of Legends and is considered the best library for the Riot Games API by most of the community, along side Cass's sister library Orianna. I work on Cass and Ori with Rob Rua under the guise of Meraki Analytics, our for-fun startup company.


### LazyLists

https://github.com/meraki-analytics/merakicommons/blob/master/merakicommons/container.py#L323

A `LazyList` is a generator-backed list that lazily generates the items in the list. The lazy functionality is useful when you have a large (or expensive-to-compute) list that you may only need the first few elements of. Typically in python we use a generator to generate expensive-to-compute or high-memory elements. Generators are useful because they the compute elements on-demand and do not store the elements in memory after being iterated over. In some cases, however, we may want to reuse the elements in a generator. For example, we use `LazyList`s in Cassiopeia for paginated data; the user can access the data as if it existed in a list, and we request the data on a need-to-use basis because we recieve the data in a pages (because the incoming data is paginated).

Example usage:

    def expensive_to_compute_items():
        for i in range(0, 100):
            time.sleep(5) # each item takes 5 seconds to compute
            yield i

    my_lazy_list = LazyList(generator=expensive_to_compute_items())

    fifth_item = my_lazy_list[4]  # takes a while to compute
    first_five_items = my_lazy_list[:5]  # instantaneous


### League of Legends Champion Role Identification

https://github.com/meraki-analytics/role-identification

In the game League of Legends, five players choose champions to play on a team. These champions play different roles in the game, but those roles are flexible and depend on goals of the player in addition to the unique aspects of the champion. My Role Identification package calculates the most probable role assignments for the five champions on the team.

You can think of it like basketball players on the court. Basketball typically has a point guard, a shooting guard, a small forward, a power forward, and a center. The five champions on a team in League each play their own roles, but unlike basketball, the champions (players) can flex between different roles from game to game. My code helps users identify what champions played what role in each game, which helps with a consistent UX experience and with accurate calculations of statistics.


### Motif Extraction

https://github.com/paul-voyles/motifextraction

The motif extraction package identifies the structure of disordered atomic systems using complex machine learning clustering algorithms. I developed this code over the course of my PhD work. Paul Voyles is my thesis advisor, so this work is on his account for the sake of longevity. Using motif extraction, I was able to identify a new structure in metallic glasses that controls the physics of the system.


### StructOpt v2

https://github.com/uw-cmg/StructOpt/tree/master/v2-experiments-and-energy

StructOpt is a Structure Optimization suite designed for materials with complicated structure. It uses genetic algorithms to efficiently sample the massive domain space of atomic systems. StructOpt was developed in collaboration with other researchers, with myself as the main architect, during my PhD work.


### FEMSIM/HRMC

https://github.com/paul-voyles/femsim-hrmc

Hybrid Reverse Monte Carlo (HRMC) is a Monte Carlo structure simulation package. It uses fluctuation electron microscopy (FEM) data and energetic potentials to constrain the structure of a material, thereby generating atomic structures that are consistent with experimental FEM data and that have realistic bond lengths and geometries. I contributed to significantly this package during my PhD. Paul Voyles is my thesis advisor, so this work is on his account for the sake of longevity.

