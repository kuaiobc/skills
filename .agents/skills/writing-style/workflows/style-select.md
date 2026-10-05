# Style Select

Select a document Profile first, then a style Preset. Load profile constraints
from `profiles/` and preset weights from `config/presets.yaml` or a named file
in `presets/`. A preset file may extend a base preset; apply its explicit values
after loading the base. Keep profile constraints and style preferences separate
in the effective Style IR.

Explicit user requirements take precedence over profile and preset preferences,
unless they conflict with factual correctness or hard task constraints.

Numeric ratios are mapped to tendencies, not sentence quotas.
The shorthand `70/10/20` means structure/tone/skepticism and selects
`presets/70-10-20.yaml`; inherit its base preset for dimensions it does not
specify. Named dimension values such as `calmness=85` remain independent
overrides.
