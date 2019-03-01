```json
{
	"Discord Command": {
		"prefix": "dcommand",
		"description": "create discord bot command class ",
		"body": [
			"<?php",
			"",
			"return function (\\$client) {",
			"\treturn (new class(\\$client) extends \\CharlotteDunois\\Livia\\Commands\\Command",
    	"\t{",
      "\t\tfunction __construct(\\CharlotteDunois\\Livia\\LiviaClient \\$client)",
      "\t\t{",
      "\t\t\tparent::__construct(\\$client, array(",
      "\t\t\t\t'name' => '$1', // Give command name", 
      "\t\t\t\t'aliases' => array(),",
      "\t\t\t\t'group' => '$2', // Group in ['command', 'util']", 
      "\t\t\t\t'description' => '$3', // Fill the description", 
      "\t\t\t\t'guildOnly' => false,",
      "\t\t\t\t'throttling' => array(",
      "\t\t\t\t\t'usages' => 5,",
      "\t\t\t\t\t'duration' => 10",
      "\t\t\t\t),",
      "\t\t\t\t'guarded' => true,",
      "\t\t\t\t'args' => array( // If you need some variables you should either fill this section or remove it", 
      "\t\t\t\t\tarray(",
      "\t\t\t\t\t\t'key' => 'memberr',",
      "\t\t\t\t\t\t'label' => 'memberr',",
      "\t\t\t\t\t\t'prompt' => 'What memeber do you mean?',",
      "\t\t\t\t\t\t'type' => 'member'",
      "\t\t\t\t\t)",
      "\t\t\t\t)",
      "\t\t\t));",
      "\t\t}",
			"",
      "\t\tfunction run(\\CharlotteDunois\\Livia\\CommandMessage \\$message, \\ArrayObject \\$args, bool \\$fromPattern)",
      "\t\t{",
      "\t\t\treturn  \\$message->say('...');",
      "\t\t}",
    	"\t});",
			"};"	
			]
	}
}
```