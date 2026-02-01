# Thoughts while learning formae

Formae was brought up as an interesting infra project for some future use cases, so I figured I'd take a peak
and see what all the hype was about. This project documents my learning journey

## Wait... it's just an abstraction on top of a persistent agent?

https://docs.formae.io/en/latest/configuration/ undoes a lot of the initial magic this tool promises.
If it's just an agent that polls your infrastructure and stores state in a DB... how is it any different
than OpenTofu/Terragrunt with some extra steps?

## Wait - it's just an abstraction on top of OpenTofu-esque type-safe definitions, that can be abused in the same ways OpenTofu can?

Per their [schema](https://github.com/platform-engineering-labs/formae-plugin-aws/blob/main/schema/pkl/ec2/subnet.pkl), it looks like not all resources do their auto-resolution feature, and they have to explicitly call out formae.Resolvable

## Confirm isn't optional

That's it. The description field not making confirmation an optional that is true by default is... a decision

## It doesn't support any restricted regions

No mention of GovCloud or iso regions. Restricted regions eat your heart out.

## There's no way to update a config you made once it's made?!

Keep getting errors related to this

## Profiles must be explicitly configured

No support for configuring profiles via standard AWS SDK commands

## Changes don't trigger an update with the agent

I changed tags on both things, and it didn't update anything
