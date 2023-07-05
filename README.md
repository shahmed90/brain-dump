# Brain dump

## Initialize

- Install requirements via asdf with `asdf install`
- Initialize the clone with `task init`

## Use

- Run local server with `task serve` and open http:/localhost:1313/brain-dump/
- Add a new page with `task add-dump`, e.g. `task add-dump cloud/aws/iam`

## Deployment

- Comply to the `pre-commit` checks
- Push to `main` and let GH actions do their magic
