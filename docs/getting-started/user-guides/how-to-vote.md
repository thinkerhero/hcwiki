# <img class="dcr-icon" src="/img/dcr-icons/TicketVoted.svg" /> **How To Vote**

This guide assumes you already have an active wallet and have purchased tickets. If not, please follow the [Voting Preperation](/getting-started/user-guides/agenda-voting/#voting-preparation) guide.

The choice a ticket votes with depends on your vote preference at the time the ticket is chosen, not when it is bought. So you can set your choice at any time within the voting window and all future tickets will vote accordingly.

## <img class="dcr-icon" src="/img/dcr-icons/Pool.svg" /> **Stakepool Voting**

If your Stakepool has updated to the latest stakepool software, you will find a "Voting" page in the navigation menu with dropdown options for each agenda. After you've chosen how you want your tickets to vote, simply press the "Update Voting Preferences" to save your votechoices. Below you'll find an image of the votechoices for vote version 5.

<img src="/img/stakepool-voting-page.png">

You can also update your voting preferences via Hcash. Under the Tickets section, you'll find the option to set your vote. You must be using a stake pool to use this option.

<img src="/img/decrediton/voting.png">

---------------------------

## <img class="dcr-icon" src="/img/dcr-icons/Solo.svg" /> **Solo Voting**

##I just want the commands!##

###**YES**###
`hcctl --wallet setvotechoice lnfeatures yes`

###**NO**###
`hcctl --wallet setvotechoice lnfeatures no`

----------------

Through the command line, you'll want to familiarize yourself with the `hcctl --wallet getvotechoices` and `hcctl --wallet setvotechoice "agendaid" "choiceid"` commands.

The first command, `hcctl --wallet getvotechoices`, returns JSON resembling this:

```
{
  "version": 5,
  "choices": [
    {
      "agendaid": "lnfeatures",
      "agendadescription": "Enable features defined in DCP0002 and DCP0003 necessary to support Lightning Network (LN)",
      "choiceid": "abstain",
      "choicedescription": "change to the new consensus rules"
    }
  ]
}
```

The second command, `hcctl --wallet setvotechoice "agendaid" "choiceid"`, let's you set your votechoice. `"agendaid"` is found via the `getvotechoices` command above, and `"choiceid"` can be `yes`, `no`, or `abstain`.

For example, issuing `hcctl --wallet setvotechoice lnfeatures yes` results in the following changes to `hcctl --wallet getvotechoices`:

```
{
  "version": 5,
  "choices": [
    {
      "agendaid": "lnfeatures",
      "agendadescription": "Enable features defined in DCP0002 and DCP0003 necessary to support Lightning Network (LN)",
      "choiceid": "yes",
      "choicedescription": "change to the new consensus rules"
    }
  ]
}
```
