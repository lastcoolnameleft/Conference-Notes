* Presenters
  * Chris Mullins (sr dir, bot framework)
  * Viswac Sena Kannan (Sr PM) 
  * Henrik Frystyk Nielson (Principal Arch, Bot Framework)
* Announcement:  at build, 1 yr old
  * 10M messages/day
  * 1M unique users /day
  * 100k devs
  * 10k active bots
* Why a bot/Why so popular?
  * They are adaptive.  Can talk/type to them.
  * all these canvases to talk via
* Demo
  * BotFramework.com Portal
  * "Smart Bots start here" - new doc page
    * Lang understanding with bots?
  * New Cortana Channel
    * Can reach 145M users via cortana
  * "TestBot"
    * In window, say "hi" and talk to it.
  * Announced analytics to bots
    * See message rates across channels
    * Just plug in AppInsight ID
  * Github Samples
    * github.com/Microsoft/BotBuilder
    * Cards, LUIS, Speech/ToText
    * SDK are OSS (C# + Node)
      * Just released 3.8 SDK
    * Can use Stack Overflow for support (tag with BotFramework)
* What is bot?
  * Really just REST endpoint
  * Can just start with swagger files. But easier with SDK
  * Can talk to Intelligence tools + Platform services
  * Can run in Azure, own cloud
* Bot framework - A connector
  * Talk to Skype, Bing, Direct Line, WebChat
* Highlights
  * Bot Builder
    * SDK Update: Speech, Diaglog tools, channel inspector
    * improved tooling
  * Platform 
    * New channel: Cortana, Bing, Skype for Business
    * Adaptive Cards,
    * Speech Support
    * Payments
  * Intelligence
    * Analytics
    * Bot Controls
    * Speech Support
    * Cog Serv
* New Docs!
  * #1 Requested features
* New Channels
  * 12 as of today
  * 3 new
    * Cortana - can add voice
    * Skype for Business - LoB bots, IT managed, Integrated Auth
    * Bing Business Bots 
      * e.g. if you are restaurant, can attach to bing channel and let people talk to it
* Bot Discovery
  * Big search for bots
  * Demo
    * Search for restaurant
    * Clicked on "chat bot"
      * "Do you have wifi?"
      * "Yes."  Show'ed details
    * "Contoso Cafe"
      * Could reserve table
* Adaptive Cards
  * Native looking cards.  
  * Can do SSML (W3 standard for speech)
* Payments
  * Using "Stripe" as payment integrator
  * Works across most major platforms
* Speech
  * Deep integration across bot framework
  * Speech in protocols
    * DirectLine Support, WebChat, Cortana
  * Speech in SDKs
    * SSML, Speech Friendly prompts
  * Speech in LUIS
    * Modeled conv
    * Common model (Cortana, Bing Search)
    * If using speech, can use LUIS and any of our speech recognition to "prime" the speech
* LUIS
  * Language Understanding
  * Intents + Entities to determine what action user wants to perform
  * Prod + Stg versioning
  * More lang (dutch, korean, dialetcs)
  * Increased intent + entity limits
  * Prebuilt domains
    * Predefined packages, bootstrap model creation, customizable!
    * e.g. Sports, weather, stocks
  * Demo
    * New UI + API
    * Created "values"  "fan belt, battery, tire"
      * Suggested other values in the car family
  * Added ability to use versions
  * Added "collaborators" so others can contribute
* Azure Bot Service v.Next
  * Showing sneak-peek of what we're thinking about
  * 1-stop-shop for building
  * Highlights
    * Data stays in user's sub
    * Improved perf via colocation
      * Bot + functions + LUIS runtime
    * SDK unification
    * Componentization + reuse
* Demo
  * Click "new bot"
    * Options:  Use bot builder sdk or Bot Conversation Designer
    * Provisions bot for you in your own subscription
      * Includes app insights + luis auto-created
  * Build tab is where you spend most of time.
  * All intents/entities show up in "intelligence section"
  * Visual "decision state"
  * Can create adaptive cards in browser
  * Asking bot to find coffee, it asked for location.  Able to remember location for other conversations
  * Humans are not normally structured.  We jump around conversations.
    * Azure Bot v.Next makes it easy.
    * deno'ed asking questions, and changing input data in the same sentence as confirming.
* call to action
  * build bots - dev.botframework.com
