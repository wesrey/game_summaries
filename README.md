# Game Summaries

Board Game summaries available to find via the index.html file. To add a new summary:

1. Create the game rules in `.md` Markdown format inside the `games` subfolder.
2. Add the Markdown filename to `games/games-list.json`.

For example, a file named `New Game.md` should have this entry in `games-list.json`:

```json
"New Game.md"
```

Use a similar style of starting with How to Win, Setup, what a Round and Turn look like, and Game Ending scoring.

## Automatic S3 Deployment

The `main` branch deploys to the `game_summaries/` prefix in S3 automatically through GitHub Actions. Configure these repository variables in **GitHub > Settings > Secrets and variables > Actions > Variables**:

- `AWS_REGION`: The AWS region containing the bucket, such as `us-east-1`.
- `AWS_S3_BUCKET`: The S3 bucket name.
- `AWS_ROLE_ARN`: The ARN of an AWS IAM role trusted by this GitHub repository through OIDC.

The IAM role needs permission to list the bucket and sync objects, including putting and deleting objects. The workflow can also be started manually from the repository's **Actions** tab.
