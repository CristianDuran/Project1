# Project1



using JuMP
using GLPKMathProgInterface
m = Model(solver=GLPKSolverMIP())

print(m)

@variable(m, x >= -1)
@variable(m, -3 <= y <= 5, Int)
@variable(m, z, Bin)


n = 10
@variable(m, 0 <= x[1:n] <= 3)

@constraint(m, x + y[1] >= 0)
@constraint(m, x + y[2] >= 0)
@constraint(m, x + y[3] >= 0)
