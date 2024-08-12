# Voting Module 

## Overview

The `Voting` module provides a basic implementation of a decentralized voting system using Move, a smart contract language. The module allows the deployment of a voting system where candidates can be registered, and votes can be cast by participants. The system is designed to maintain a list of candidates, keep track of votes, and declare a winner.

## Features

- **Candidate Registration**: Supports the registration of multiple candidates.
- **Voting Mechanism**: Allows participants to cast votes for their preferred candidates.
- **Vote Counting**: Keeps track of the number of votes each candidate receives.
- **Winner Declaration**: Declares the candidate with the most votes as the winner.

## Module Structure

The module contains the following key components:

- **Constants**:
  - `E_NOT_OWNER`: Error code for unauthorized access.
  - `E_IS_NOT_INITIALIZED`: Error code when the voting system is not initialized.
  - `E_DOES_NOT_CONTAIN_KEY`: Error code when a specified candidate does not exist.
  - `E_IS_INITIALIZED`: Error code when the voting system is already initialized.
  - `E_IS_INITIALIZED_WITH_CANDIDATE`: Error code when a candidate is already initialized.
  - `E_WINNER_DECLARED`: Error code when a winner is already declared.
  - `E_HAS_VOTED`: Error code when a participant has already voted.

- **Structs**:
  - `Candidate`: Represents the state of the voting system, including:
    - `candidate_list`: A map of candidate addresses to their respective vote counts.
    - `candidate`: A vector containing the list of candidate addresses.
    - `winner`: The address of the declared winner.

## Usage

1. **Initialization**:
   - The voting system needs to be initialized before any candidates can be registered or votes cast.

2. **Candidate Registration**:
   - Candidates are registered in the system by adding their addresses to the `candidate_list`.

3. **Casting Votes**:
   - Participants can cast their votes by specifying the candidate's address. Each participant is allowed to vote only once.

4. **Winner Declaration**:
   - Once voting is completed, the system calculates the votes and declares the candidate with the most votes as the winner.

## Error Handling

The module includes various error codes to handle different scenarios, such as unauthorized access, uninitialized states, and duplicate voting attempts. These error codes are used to ensure the integrity and proper functioning of the voting system.

## Example Usage

To use this module, you would typically follow these steps in a script:

1. Initialize the voting system.
2. Register candidates.
3. Allow participants to cast votes.
4. Declare the winner once all votes are cast.

## Dependencies

- `std::signer`: Used for managing access and permissions.
- `std::vector`: Utilized for handling lists of candidates.
- `std::simple_map::SimpleMap`: A simple key-value store for managing vote counts.


