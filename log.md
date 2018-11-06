# 100 Days Of Code - Log

### Day 1: November 2, Friday

**Today's Progress**: I set up the git repository and boilerplate code for my React project, ChaiCMS. I upgraded the packages in package.json that were outdated from the Udemy React course. This caused issues with webpack that I went through and fixed.

**Thoughts:** I thought diving by myself into webpack once everything broke after the upgrades was going to be really scary since I am new to webpack config, but it wasn't too bad. Some googling and documentation reading got me going in the right direction. It was great seeing the dev server fire up successfully after getting everything set up.

**Link(s) to work:** [ChaiCMS](https://github.com/ndjamenamarmon/chaicms)


### Day 2: November 3, Saturday

**Today's Progress**: I created the Sidebar component for ChaiCMS, hard-coding the links for the moment to point to the dashboard page. I added initial styles for the layout. I then created the Settings page and settings form, adding functionality to edit and display the site title and site description, integrating with the Firebaase database.

**Thoughts:** I feel like I made fast progress building out the components I worked on today, helped by the boilerplate project from the React Udemy course I just completed. So far, I am feeling pretty comfortable modifying the boilerplate code to build what I need. Tomorrow I plan on creating the tests for the Sidebar and Settings components, actions, and reducers.

**Link(s) to work:** [PR #2](https://github.com/ndjamenamarmon/chaicms/pull/2)


### Day 3: November 4, Sunday

**Today's Progress**: I built out Content Types, Fields, and the start of Entries for ChaiCMS, including updating the Sidebar to populate content types dynamically. I built a basic integration of fields with content types.

Just before bed, I looked into the new React Hooks API and switched two class components (the SettingsForm and ContentTypeForm) over to functional components using Hooks. I for the second form, I created a custom hook, useSlugify.

**Thoughts:** I know I was planning on building out all the tests for the Sidebar and Settings components, actions, and reducers today, but I found myself much more interested in building rather than testing. I will need to build out the tests at some point, but it is interesting observing myself and my tendencies. I love working with the more visual aspects of coding and being able to see what I am creating. Tests seem more like a "have to do" task rather than a "want to do."

So far, I'm liking Hooks. They seem cleaner and more straightforward than the Class component method of handling state. Moving away from using this for state and props is nice, as is being able to use custom hooks that can be re-used in different components.

**Link(s) to work:**
- [Added basic Content Types functionality](https://github.com/ndjamenamarmon/chaicms/commit/afc570f367e1186f85ef2ad17962f1b7bc0e1d08)
- [Moved Content Types to folder](https://github.com/ndjamenamarmon/chaicms/commit/eb54e61b0d6763541e7591cdfba597b4ed27400f)
- [Added Fields functionality and basic integration with content types](https://github.com/ndjamenamarmon/chaicms/commit/0026a96b160c260af939abd2eb7ad4d6da7be4d5)
- [Added files for Entries](https://github.com/ndjamenamarmon/chaicms/commit/5633a4af3a19e8aed90f298be238cded9886aeda)
- [Changed SettingsForm to function component with hooks](https://github.com/ndjamenamarmon/chaicms/commit/b9e8a71dfdea13cc68c4baf2f6876c13428c3fb0)
- [Changed ContentTypeForm to functional component with Hooks, created custom useSlugify hook](https://github.com/ndjamenamarmon/chaicms/commit/7c1fa8d44f2f045bb60d86ab551898b0b346c30b)


### Day 4: November 5, Monday

**Today's Progress**: Today I continued building out the Entries functionality for ChaiCMS, focusing on the EntryForm. I changed the EntryForm component from a class component to a function component, and implemented Hooks to handle state.

**Thoughts:** Working with the Entries functionality is an interesting challenge since they are meant to have dynamic fields. Unlike Content Types or Fields, I don't know what the fields are going to be, so I have to build with that in mind. Up to now I have been outputting form fields and object properties that I know the object must have, but with Entries the object properties could be anything. 

I am loving working with Hooks. Changing from the Class component to the Function component was a relief and I had to think about this.props.whatever and this.state.whatever less, and just code!

**Link(s) to work:** [Changed EntryForm to functional components with Hooks, started building it out; fixed some bugs](https://github.com/ndjamenamarmon/chaicms/commit/31431f057ce08c42fb43162dd6787e7002d4d5f1)


### Day 5: November 6, Tuesday

**Today's Progress**: Today I continued building out the Entries functionality for ChaiCMS, working on handling the EntryForm submission of data to the database. I also worked on implementing the list of entries per content type. 

**Thoughts:** Submitting entry data was an interesting little challenge since the fields and consequently key-value pairs in each entry object could vary and would need to be dynamic depending on the fields available for the content type. I had an issue where React didn't like me updating the entry state whose initial value was an empty object ```{}``` but when edited had key value pairs. It was expecting the empty state to already have those keys with some default data: ```{ key: "" }```.

I tried using a useEffect() hook to populate the state immediately after render and before the text input was used by the user, but that didn't work either. I then passed the calculated state (with all keys that would be used based on the fields available in the content type) from the parent component as a prop and passed that into useState() as the default state, and that worked well. 

**Link(s) to work:**
- [Add entry functionality and saving to db](https://github.com/ndjamenamarmon/chaicms/commit/9c4aeb817895bafdb4469fda8a33390d218885aa)
- [Wired up Entries List on Entries page](https://github.com/ndjamenamarmon/chaicms/commit/0178c875dfc7d155b21ff20e158af9cecd4684f4)
