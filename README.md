# Jira Tools

## Installation

```Shell
go install jira-tools
```

## Usage

### Unblocked Issues

`unblocked` will search the specified project for issues whose blocking dependency is complete or in progress. This is useful for support projects linked to developer issues.

```Shell
Usage:
  jira-tools unblocked [flags]

Flags:
  -h, --help             help for unblocked
  -p, --project string   Jira project to use
  -v, --verbose          verbose output
```

### Release Notes

`releasenotes` will generate release notes from the comma-separated list of projects supplied. Using the flags, the program can generate release notes from active sprints or sprints in the past. The program defaults to the most recently closed sprint. It defaults to Markdown output, but can also be set to generate Confluence Wiki text.

```Shell
Usage:
  jira-tools releasenotes [flags]

Flags:
  -a, --active            create release notes for the active sprint
  -c, --confluence        output in confluence wiki format, defaults to markdown
  -h, --help              help for releasenotes
  -p, --projects string   comma-separated list of Jira Projects to evaluate
  -s, --separate          separate the projects out into individual release notes
  -b, --sprintsback int   number of sprints to look back (defaults to 0, most recent completed sprint)
```

### Service Desk Issues

`servicedesk` will generate a comma-separated list of issues in the specified project that were created in a specified time period. Using the flags, the program can output to a CSV file or, if no output filename is given, output to the console.

```Shell
Usage:
  jira-tools servicedesk [flags]

Flags:
  -d, --days int         Days of history to retreive (default 7)
  -h, --help             help for servicedesk
  -o, --output string    CSV File to output
  -p, --project string   Jira project to use
```
