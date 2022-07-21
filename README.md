    EVENTS: When we update a dynamic object like an array or a mapping, we want to emit event.
     logging and events
     EVM can emit log, we can read the logs from a node, we can make eth_getLogs call to get the logs
     inside logs, there are important piece of logging called events
     Events allows us to "print" information to the loging structure in a way that's more gas efficient and saving into storage variable
     Event and logs live in special data structure that isn't accessible to smart contracts, that's why it's cheaper, cos smart contracts can't access them
     trade off (Advantage) >> we can print info that we need without having to save it in the storage variable which would require more gas
     each event are tied to smart contracts or account addresses that emmitted those events in the transactions

     Listening to the events are helpful > transactions happens > event is emitted taht we can listen to > this is how offChian events work
     Chianlink node listens for events for request data events to get a number, make API calls

     Need to index the events
     Graph listens to them and stores them in graph > easy to query later on

    example:
    event storedNumber)
        uint256 indexed oldNumber,
        uint256 indexed newnumber,
        uint256 addedNumber,
        adderss sender,
        );
        // When we emit this event, it's goin to have these parameters: (1) Indexed parameters, and (2) Non-indexed parameters
        // can have up to 3 index parameters, also known as 'Topics'
        // Indexed parameters are much easier to search for, amd easier to query
        // eth_getLogs function has parameters to search for specific topics,
        // Non-indexed are harder to search because they are abi encoded and requires abi to search
