INICIO
    CLASE TripStop {
        originAddress : Address
        destinationAddress : Address
        status : TripStopStatus
        estimatedTime : LocalTime
        distance : double
        stopOrder : Integer
        +startTripStop()
        +finishTripStop()
        -calculateEstimatedAndDistance()
    }

    PROCESO calculateEstimatedAndDistance()
        GET tripInfo = DistanceMatrixApi(originAddress, destinationAddress)
        setEstimatedTime(tripInfo.getEstimatedTime())
        setDistance(tripInfo.getDistance())

    INTERFACE StopStrategy
        calculateStopsEstimatedTime(List<TripStop> stops) : List<Integer>

    CLASE StopXMinutes implements StopStrategy {
        minutes : Integer
        
        StopXMinutes(Integer minutes)

        PROCESO List<Integer> calculateStopsEstimatedTime(List<TripStop> stops)
            FOR EACH stop in stops
                stop.setEstimatedTime(stop.getEstimatedTime + minutes)
    }



FIN