#int numberOfSamples = 1_000_000;
int probability = 10;
int howManyTimesInvoked = 
  Stream.generate(() -> randomInvoker.withProbability(() -> 1, () -> 0, probability))
    .limit(numberOfSamples)
    .mapToInt(e -> e)
    .sum()
