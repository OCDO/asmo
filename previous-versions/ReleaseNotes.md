# ASMO Release Notes

Atomistic Simulation Methods Ontology (ASMO)

---

## v0.3.0

Expansion to cover workflows of stacking fault energy calculations.

### New Classes (5)
- `SpatialTransformation` — new top-level class for geometric transformations
- `Rotation` — subclass of `SpatialTransformation`
- `Shear` — subclass of `SpatialTransformation`
- `Translation` — subclass of `SpatialTransformation`
- `ANNNImodel` — Axial Next-Nearest-Neighbour Ising model, added as a computational method

### New Object Properties (2)
- `hasPlane` — links a simulation or transformation to a crystallographic plane
- `hasShearPlane` — links a shear operation to its plane of application

---

## v0.2.0

Major expansion of the ontology from 32 to 100 classes. This release introduces a broad vocabulary for physical quantities, simulation parameters, mechanical properties, and mathematical operations.

### New Classes (71)

**Simulation & Methodology**
- `Simulation`, `SimulationAlgorithm`, `MolecularStatics`, `StructureManipulation`
- `ComputationalSample`, `SimulationCell`, `SimulationCellLength`, `SimulationCellVolume`
- `SimulationParameter`, `SimulationRunTime`, `SimulationTime`, `TimeStep`, `NumberOfIonicSteps`
- `PeriodicBoundaryCondition`, `KPointMesh`, `EnergyCutoff`
- `Barostat`, `Thermostat`
- `OutputParameter`
- `QuasiHarmonicApproximation`, `ThermodynamicIntegration`, `FreeEnergyCalculation`, `EnergyCalculation`, `EquationOfStateFit`
- `PointDefectCreation`, `MolecularForceField`, `StillingerWeberPotential`

**Physical Quantities**
- `PhysicalQuantity`, `Energy`, `PotentialEnergy`, `KineticEnergy`, `TotalEnergy`, `FreeEnergy`
- `GibbsFreeEnergy`, `HelmholtzFreeEnergy`, `ThermodynamicFreeEnergy`, `FormationEnergy`
- `Force`, `Pressure`, `VirialPressure`, `Temperature`, `Volume`, `VolumeRange`
- `Length`, `Mass`, `Time`, `Strain`, `StrainRate`, `Stress`
- `SpecificHeatCapacity`, `ThermalExpansionCoefficient`, `TotalMagneticMoment`
- `Vector`, `Plane`

**Mechanical Properties**
- `BulkModulus`, `ShearModulus`, `YoungsModulus`, `PoissonsRatio`
- `ElasticConstant`, `ElasticTensor`
- `FlowStress`, `YieldStress`
- `Nanoindentation`, `CompressionTest`, `Tensile_Test`

**Mathematical Operations**
- `MathematicalOperation`, `Addition`, `Subtraction`, `Multiplication`, `Division`, `Exponentiation`

### Removed Classes (3)
- `DensityFunctionalTheoryMethod` — subsumed into the DFT hierarchy
- `EnergyDifferenceCalculation` — replaced by more specific energy calculation classes
- `StructureOptimization` — reorganized under `SimulationAlgorithm`

### New Object Properties (5)
- `hasCalculatedProperty` — links a simulation to its output calculated property
- `hasOutputParameter` — links a workflow to output parameters
- `hasSimulationParameter` — links a simulation to its parameters
- `hasVector` — associates a simulation cell or quantity with a vector
- `usesSimulationAlgorithm` — links a computational method to the algorithm used

### New Datatype Properties (12)
Mathematical operand and result properties for the new `MathematicalOperation` hierarchy: `hasAddend`, `hasBase`, `hasDifference`, `hasDividend`, `hasDivisor`, `hasExponent`, `hasFactor`, `hasMinuend`, `hasProduct`, `hasQuotient`, `hasSubtrahend`, `hasSum`

### Metadata
- Added schema.org annotation properties (affiliation, citation, email, familyName, givenName, funder, etc.)
- Added Dublin Core terms: `abstract`, `created`, `issued`, `modified`, `license`
- Added IAO annotation properties and OBCS mathematical formula annotation
- Added `bibo:doi` annotation property

---

## v0.0.1

Initial release of ASMO.

### Classes (32)
Core computational method hierarchy: `ComputationalMethod`, `DensityFunctionalTheory`, `MolecularDynamics`, `AbInitioMolecularDynamics`, `MonteCarloMethod`, `KineticMonteCarloMethod`

XC functionals: `ExchangeCorrelationEnergyFunctional`, `LocalDensityApproximation`, `GeneralizedGradientApproximation`, `MetaGeneralizedGradientApproximation`, `HybridFunctional`, `HybridGeneralizedGradientApproximation`, `HybridMetaGeneralizedGradientApproximation`

Interatomic potentials: `InteratomicPotential`, `EmbeddedAtomModel`, `ModifiedEmbeddedAtomModel`, `MachineLearningPotential`, `Lennard-JonesPotential`

Other: `CalculatedProperty`, `InputParameter`, `RelaxationDOF`, `StatisticalEnsemble`, `Unit`, `StructureOptimization`, `EnergyDifferenceCalculation`, `DensityFunctionalTheoryMethod`

PROV-O classes imported: `prov#Activity`, `prov#Agent`, `prov#Entity`, `prov#Organization`, `prov#Person`, `prov#SoftwareAgent`

### Object Properties (18)
`hasComputationalMethod`, `hasInputParameter`, `hasInteratomicPotential`, `hasRelaxationDOF`, `hasStatisticalEnsemble`, `hasUnit`, `hasXCFunctional`, `wasCalculatedBy`, plus PROV-O properties

### Datatype Properties (4)
`hasReference`, `hasValue`, `prov#startedAtTime`, `prov#endedAtTime`
