# The-Paints

In a lively art supply store, a talented artist named "Leo" was on a mission to purchase some vibrant paints for his latest masterpiece. The shop offered two types of paints: ruby red and sapphire blue. A jar of ruby red paint cost X rupees, while a jar of sapphire blue paint was priced at Y rupees.
Leo planned to buy exactly N jars of paint, but he had a specific requirement: he wanted at least K jars to be ruby red. With a tight budget Leo aimed to calculate the least amount of money he would need to spend to fulfill his artistic vision. Can you help Leo figure out the best way to make his purchase?

Input
The first line of input will contain a single integer T, denoting the number of test cases. Each test case consists of a single line containing four space- separated integers N, K, X, Y.

Constraints
1 ≤ T ≤ 10^3
1 ≤ N ≤ 10^8
0 ≤ K ≤ N
1 ≤ X, Y ≤ 10
Output
For each test case, output on a new line the least amount of money Leo needs to pay in order to buy N jars of paint such that at least K of the jars bought are red.

def calculate_minimum_cost(t, test_cases):

    results = []
    for case in test_cases:
        N, K, X, Y = case
        # If X <= Y, it's cheaper to buy red jars, buy all as red jars
        if X <= Y:
            cost = N * X
        else:
            # Buy at least K red jars, the rest as blue jars
            cost = K * X + (N - K) * Y
        results.append(cost)
    return results

# Input reading
T = int(input())
test_cases = []
for _ in range(T):
    test_cases.append(tuple(map(int, input().split())))

# Process and output results
results = calculate_minimum_cost(T, test_cases)
for result in results:
    print(result)
