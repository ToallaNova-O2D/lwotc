---


---

<h1 id="xcom-2-war-of-the-chosen-—-complete-codebase-knowledge-base">XCOM 2: War of the Chosen — Complete Codebase Knowledge Base</h1>
<blockquote>
<p><strong>5,087 UnrealScript classes</strong> + <strong>16 macro files (.uci)</strong> distributed across <strong>45 packages</strong><br>
Engine: Unreal Engine 3 (UnrealScript) | Generated: 2026-05-28</p>
</blockquote>
<hr>
<h2 id="table-of-contents">Table of Contents</h2>
<ol>
<li><a href="#1-global-package-architecture">Global Package Architecture</a></li>
<li><a href="#2-class-hierarchy">Class Hierarchy — Depth Analysis</a></li>
<li><a href="#3-gamestate-system">GameState System — Core Architecture</a></li>
<li><a href="#4-tactical-combat-system">Tactical Combat System</a></li>
<li><a href="#5-strategic-layer">Strategic Layer (Geoscape/Avenger)</a></li>
<li><a href="#6-artificial-intelligence-system">Artificial Intelligence System</a></li>
<li><a href="#7-ui-system">UI System</a></li>
<li><a href="#8-event-system">Event System</a></li>
<li><a href="#9-global-macro-system">Global Macro System (.uci)</a></li>
<li><a href="#10-template-system">Template System and Data-Driven Design</a></li>
<li><a href="#11-dlcs-and-expansions">DLCs and Expansions</a></li>
<li><a href="#12-community-highlander">Community Highlander</a></li>
<li><a href="#13-engine-fundamental-classes">Engine — Fundamental Classes</a></li>
<li><a href="#14-architectural-patterns">Architectural Patterns</a></li>
<li><a href="#15-navigation-guide">Navigation Guide by System</a></li>
<li><a href="#16-complexity-analysis">Complexity Analysis and Optimization</a></li>
<li><a href="#17-global-statistics">Global Statistics</a></li>
<li><a href="#18-optimization-guide">Practical Optimization Guide</a></li>
</ol>
<hr>
<h2 id="global-package-architecture">1. Global Package Architecture</h2>
<h3 id="package-classification">1.1 Package Classification</h3>

<table>
<thead>
<tr>
<th>Type</th>
<th>Packages</th>
<th>Classes</th>
<th>Functions</th>
<th>Lines</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Base Game</strong></td>
<td>15</td>
<td>4,164</td>
<td>33,559</td>
<td>915,714</td>
</tr>
<tr>
<td><strong>Highlander</strong></td>
<td>1</td>
<td>9</td>
<td>~20</td>
<td>~300</td>
</tr>
<tr>
<td><strong>Mods (LWOTC etc.)</strong></td>
<td>29</td>
<td>913</td>
<td>~5,000</td>
<td>~90,000</td>
</tr>
<tr>
<td><strong>Total</strong></td>
<td>45</td>
<td>5,087</td>
<td>~38,500</td>
<td>~1,006,000</td>
</tr>
</tbody>
</table><h3 id="base-game-packages-by-size">1.2 Base Game Packages (by size)</h3>

<table>
<thead>
<tr>
<th>Package</th>
<th>Classes</th>
<th>Functions</th>
<th>Lines</th>
<th>Purpose</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>XComGame</strong></td>
<td>2,498</td>
<td>28,145</td>
<td>714,314</td>
<td>All XCOM 2 game logic</td>
</tr>
<tr>
<td><strong>Engine</strong></td>
<td>1,234</td>
<td>3,448</td>
<td>140,612</td>
<td>Unreal Engine 3 base</td>
</tr>
<tr>
<td><strong>UnrealEd</strong></td>
<td>189</td>
<td>45</td>
<td>8,604</td>
<td>Engine editor (GenericBrowserTypes, etc.)</td>
</tr>
<tr>
<td><strong>DLC_2</strong></td>
<td>59</td>
<td>422</td>
<td>15,134</td>
<td>Alien Hunters (Alien Rulers, Icarus Armor, etc.)</td>
</tr>
<tr>
<td><strong>DLC_3</strong></td>
<td>57</td>
<td>355</td>
<td>10,595</td>
<td>Shen’s Last Gift (SPARK units)</td>
</tr>
<tr>
<td><strong>IpDrv</strong></td>
<td>26</td>
<td>258</td>
<td>6,939</td>
<td>Networking/IP driver</td>
</tr>
<tr>
<td><strong>GameFramework</strong></td>
<td>17</td>
<td>52</td>
<td>2,156</td>
<td>Generic game framework</td>
</tr>
<tr>
<td><strong>GFxUI</strong></td>
<td>17</td>
<td>142</td>
<td>1,736</td>
<td>Scaleform GFx UI bindings</td>
</tr>
<tr>
<td><strong>AkAudio</strong></td>
<td>16</td>
<td>0</td>
<td>424</td>
<td>Audiokinetic Wwise integration (all native)</td>
</tr>
<tr>
<td><strong>XComEditor</strong></td>
<td>17</td>
<td>26</td>
<td>419</td>
<td>XCom-specific editing tools</td>
</tr>
<tr>
<td><strong>TLE</strong></td>
<td>11</td>
<td>112</td>
<td>4,324</td>
<td>Tactical Legacy Pack</td>
</tr>
<tr>
<td><strong>Core</strong></td>
<td>11</td>
<td>185</td>
<td>3,016</td>
<td>Fundamental engine classes (Object, etc.)</td>
</tr>
<tr>
<td><strong>OnlineSubsystemSteamworks</strong></td>
<td>6</td>
<td>368</td>
<td>7,190</td>
<td>Steam integration</td>
</tr>
<tr>
<td><strong>GFxUIEditor</strong></td>
<td>4</td>
<td>0</td>
<td>257</td>
<td>Scaleform editor</td>
</tr>
<tr>
<td><strong>DLC_1</strong></td>
<td>2</td>
<td>1</td>
<td>94</td>
<td>Anarchy’s Children (cosmetic only)</td>
</tr>
</tbody>
</table><h3 id="base-package-dependencies">1.3 Base Package Dependencies</h3>
<pre><code>Core (Object, fundamental types)
  └── Engine (Actor, Component, Pawn, Controller, World, ...)
       └── GameFramework (GameInfo, GameTypes)
       └── GFxUI (Scaleform bindings)
       └── IpDrv (Networking)
       └── AkAudio (Audio engine)
            └── XComGame (ALL game logic)
                 ├── DLC_1 (cosmetic)
                 ├── DLC_2 (Alien Hunters)
                 ├── DLC_3 (SPARK / Shen's Last Gift)
                 ├── TLE (Tactical Legacy Pack)
                 └── X2WOTCCommunityHighlander (modding hooks)
</code></pre>
<hr>
<h2 id="class-hierarchy">2. Class Hierarchy</h2>
<h3 id="inheritance-depth-distribution">2.1 Inheritance Depth Distribution</h3>

<table>
<thead>
<tr>
<th>Depth</th>
<th>Classes</th>
<th>Percentage</th>
<th>Example</th>
</tr>
</thead>
<tbody>
<tr>
<td>0</td>
<td>46</td>
<td>1.1%</td>
<td><code>Object</code>, <code>object</code> (roots)</td>
</tr>
<tr>
<td>1</td>
<td>365</td>
<td>8.8%</td>
<td><code>Actor</code>, <code>SequenceOp</code>, <code>X2DataTemplate</code></td>
</tr>
<tr>
<td>2</td>
<td>1,031</td>
<td>24.8%</td>
<td><code>UIScreen</code>, <code>X2Effect</code>, <code>SequenceAction</code></td>
</tr>
<tr>
<td>3</td>
<td>1,223</td>
<td>29.4%</td>
<td><code>X2Effect_Persistent</code>, <code>XComGameState_BaseObject</code></td>
</tr>
<tr>
<td>4</td>
<td>975</td>
<td>23.4%</td>
<td><code>XComGameState_Unit</code>, <code>UIPanel</code></td>
</tr>
<tr>
<td>5</td>
<td>321</td>
<td>7.7%</td>
<td><code>X2Ability_DefaultAbilitySet</code>, <code>UIMission</code></td>
</tr>
<tr>
<td>6</td>
<td>125</td>
<td>3.0%</td>
<td><code>UIFacility_Armory</code>, <code>XComHumanPawn</code></td>
</tr>
<tr>
<td>7</td>
<td>68</td>
<td>1.6%</td>
<td><code>SeqEvent_AbilityTriggered</code></td>
</tr>
<tr>
<td>8</td>
<td>5</td>
<td>0.1%</td>
<td><code>XComMPLobbyGRI</code>, <code>UIFacility_HuntersLodge</code></td>
</tr>
<tr>
<td>9</td>
<td>5</td>
<td>0.1%</td>
<td><code>XComCivilian</code>, <code>XComGatekeeper</code>, <code>XComSectopod</code></td>
</tr>
</tbody>
</table><h3 id="deepest-inheritance-chains-9-levels">2.2 Deepest Inheritance Chains (9 levels)</h3>
<pre><code>XComCivilian → XComHumanPawn → XComUnitPawn → XComLocomotionUnitPawn 
  → XComUnitPawnNativeBase → XComPawn → GamePawn → Pawn → Actor → Object

XComGatekeeper → XComAlienPawn → XComUnitPawn → XComLocomotionUnitPawn
  → XComUnitPawnNativeBase → XComPawn → GamePawn → Pawn → Actor → Object
</code></pre>
<h3 id="top-50-most-extended-base-classes">2.3 Top 50 Most Extended Base Classes</h3>

<table>
<thead>
<tr>
<th>Base Class</th>
<th>Children</th>
<th>Domain</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Object</strong></td>
<td>343</td>
<td>Everything: Utilities, managers, data structures</td>
</tr>
<tr>
<td><strong>SequenceAction</strong></td>
<td>273</td>
<td>Kismet nodes for level scripting</td>
</tr>
<tr>
<td><strong>Actor</strong></td>
<td>172</td>
<td>World objects with position/behavior</td>
</tr>
<tr>
<td><strong>X2Action</strong></td>
<td>151</td>
<td>Visualization actions (animations, FX)</td>
</tr>
<tr>
<td><strong>UIScreen</strong></td>
<td>137</td>
<td>Full UI screens</td>
</tr>
<tr>
<td><strong>UIPanel</strong></td>
<td>128</td>
<td>UI components/widgets</td>
</tr>
<tr>
<td><strong>X2Effect_Persistent</strong></td>
<td>118</td>
<td>Combat effects lasting multiple turns</td>
</tr>
<tr>
<td><strong>MaterialExpression</strong></td>
<td>115</td>
<td>Material editor nodes</td>
</tr>
<tr>
<td><strong>X2Ability</strong></td>
<td>68</td>
<td>Ability definitions</td>
</tr>
<tr>
<td><strong>XComGameState_BaseObject</strong></td>
<td>64</td>
<td>Persistent state objects</td>
</tr>
<tr>
<td><strong>X2StrategyElement</strong></td>
<td>54</td>
<td>Strategic layer elements</td>
</tr>
<tr>
<td><strong>GenericBrowserType</strong></td>
<td>47</td>
<td>Editor browser types</td>
</tr>
<tr>
<td><strong>X2Condition</strong></td>
<td>45</td>
<td>Ability conditions</td>
</tr>
<tr>
<td><strong>AnimNotify</strong></td>
<td>43</td>
<td>Animation notifications</td>
</tr>
<tr>
<td><strong>SequenceEvent</strong></td>
<td>43</td>
<td>Kismet events</td>
</tr>
<tr>
<td><strong>X2Effect</strong></td>
<td>36</td>
<td>Instant combat effects</td>
</tr>
<tr>
<td><strong>PrimitiveComponent</strong></td>
<td>35</td>
<td>Renderable components</td>
</tr>
<tr>
<td><strong>X2StrategyElementTemplate</strong></td>
<td>33</td>
<td>Strategy templates</td>
</tr>
<tr>
<td><strong>X2Item</strong></td>
<td>33</td>
<td>Item/weapon definitions</td>
</tr>
<tr>
<td><strong>Volume</strong></td>
<td>32</td>
<td>World volumes (trigger, blocking, etc.)</td>
</tr>
<tr>
<td><strong>ActorFactory</strong></td>
<td>30</td>
<td>Editor actor factories</td>
</tr>
<tr>
<td><strong>ParticleModule</strong></td>
<td>29</td>
<td>Particle modules</td>
</tr>
<tr>
<td><strong>XComGameStateContext</strong></td>
<td>22</td>
<td>Contexts that produce state changes</td>
</tr>
<tr>
<td><strong>X2DataTemplateManager</strong></td>
<td>21</td>
<td>Template managers</td>
</tr>
<tr>
<td><strong>UIStrategyMapItem</strong></td>
<td>20</td>
<td>Strategic map items</td>
</tr>
<tr>
<td><strong>UIFacility</strong></td>
<td>19</td>
<td>Facility screens</td>
</tr>
<tr>
<td><strong>X2DataSet</strong></td>
<td>18</td>
<td>Data sets (challenge mode)</td>
</tr>
</tbody>
</table><hr>
<h2 id="gamestate-system-—-core-architecture">3. GameState System — Core Architecture</h2>
<h3 id="overview">3.1 Overview</h3>
<p>The GameState is the <strong>architectural heart</strong> of the game. All state is stored in a linear <strong>history</strong> of immutable snapshots. Each change creates a new <code>XComGameState</code> containing only the modified objects (delta).</p>
<pre><code>XComGameStateHistory (singleton)
  ├── XComGameState[0] (full initial state)
  ├── XComGameState[1] (delta: modified objects)
  ├── XComGameState[2] (delta)
  ├── ...
  └── XComGameState[N] (current state)

Each XComGameState contains:
  ├── XComGameStateContext (who/why it was created)
  └── XComGameState_BaseObject[] (modified objects)
</code></pre>
<h3 id="core-gamestate-classes">3.2 Core GameState Classes</h3>

<table>
<thead>
<tr>
<th>Class</th>
<th>Funcs</th>
<th>Lines</th>
<th>Purpose</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>XComGameState</code></td>
<td>20</td>
<td>270</td>
<td>Container for a state frame</td>
</tr>
<tr>
<td><code>XComGameStateHistory</code></td>
<td>53</td>
<td>519</td>
<td>Linear history — stores all states</td>
</tr>
<tr>
<td><code>XComGameStateContext</code></td>
<td>37</td>
<td>701</td>
<td>Abstract base: who/why a state was created</td>
</tr>
<tr>
<td><code>XComGameState_BaseObject</code></td>
<td>18</td>
<td>188</td>
<td>Base of all state objects</td>
</tr>
<tr>
<td><code>XComGameStateVisualizationMgr</code></td>
<td>56</td>
<td>934</td>
<td>Converts state changes into visualizations</td>
</tr>
<tr>
<td><code>XComGameStateNetworkManager</code></td>
<td>45</td>
<td>455</td>
<td>State synchronization in multiplayer</td>
</tr>
</tbody>
</table><h3 id="full-xcomgamestate_baseobject-hierarchy">3.3 Full XComGameState_BaseObject Hierarchy</h3>
<pre><code>XComGameState_BaseObject (18f, 188l)
├── XComGameState_Unit (546f, 15,947l) ★ THE LARGEST
│     implements: X2GameRulesetVisibilityInterface, X2VisualizedInterface,
│                 Lootable, UIQueryInterfaceUnit, Damageable, Hackable
│
├── XComGameState_Ability (138f, 4,364l)
│   └── XComGameState_Ability_CH (2f, Highlander extension)
│
├── XComGameState_Item (69f, 2,515l)
│     implements: UIQueryInterfaceItem, X2VisualizedInterface
│
├── XComGameState_Effect (61f, 2,393l)
│   ├── XComGameState_Effect_Amplify (1f)
│   ├── XComGameState_Effect_DLC_3AbsorptionField (1f)
│   ├── XComGameState_Effect_PaleHorse (1f)
│   └── XComGameState_Effect_TemplarFocus (7f)
│
├── XComGameState_GeoscapeEntity (47f, 522l) — Base of geoscape entities
│   ├── XComGameState_Airship (22f, 502l) — Flying ships
│   │   ├── XComGameState_HeadquartersXCom (331f, 9,576l) ★★
│   │   ├── XComGameState_Skyranger (14f)
│   │   └── XComGameState_UFO (31f)
│   │
│   ├── XComGameState_MissionSite (79f, 2,009l)
│   │   ├── XComGameState_MissionSiteAvengerAttack → _AvengerDefense, _ChosenAssault
│   │   ├── XComGameState_MissionSiteChosenAmbush
│   │   └── XComGameState_MissionSiteOutsideRegions → _AlienNest, _LostTowers
│   │
│   ├── XComGameState_ScanningSite (27f) — Scannable points
│   │   ├── XComGameState_BlackMarket (42f)
│   │   ├── XComGameState_Haven (31f)
│   │   ├── XComGameState_PointOfInterest (41f)
│   │   ├── XComGameState_ResourceCache (23f)
│   │   └── XComGameState_WorldRegion (93f, 2,306l) ★
│   │
│   ├── XComGameState_CovertAction (102f, 2,588l)
│   ├── XComGameState_GeoscapeCharacter
│   │   ├── XComGameState_AdventChosen (100f, 1,963l)
│   │   └── XComGameState_ResistanceFaction (94f, 1,464l)
│   │
│   ├── XComGameState_City, _Continent, _RegionLink, _TradingPost, etc.
│   └── XComGameState_AlienNetworkComponent, _Bastion
│
├── XComGameState_HeadquartersAlien (129f, 3,721l) — Global alien AI
├── XComGameState_HeadquartersResistance (84f, 2,328l)
│
├── XComGameState_HeadquartersProject (22f) — Research/construction projects
│   ├── _ProjectBuildFacility, _ProjectBuildItem, _ProjectClearRoom
│   ├── _ProjectHealSoldier (→ _ProjectHealSpark)
│   ├── _ProjectResearch (→ _ProjectProvingGround)
│   ├── _ProjectPsiTraining, _ProjectRecoverWill, _ProjectTrainRookie
│   └── _ProjectBondSoldiers, _ProjectRespecSoldier, _ProjectRemoveTraits
│
├── XComGameState_BattleData (54f, 1,574l) — Current battle data
├── XComGameState_Player (39f) — Player data
│
├── AI State Objects:
│   ├── XComGameState_AIGroup (46f, 1,850l) — AI group
│   ├── XComGameState_AIPlayerData (35f) — AI player data
│   ├── XComGameState_AIUnitData (33f) — Per-unit AI data
│   ├── XComGameState_AIBlackboard (10f) — AI blackboard
│   └── XComGameState_AIReinforcementSpawner (17f, 931l)
│
├── Facility/Staff:
│   ├── XComGameState_FacilityXCom (52f, 1,045l)
│   ├── XComGameState_FacilityUpgrade (4f)
│   ├── XComGameState_HeadquartersRoom (32f, 772l)
│   └── XComGameState_StaffSlot (42f, 768l)
│
├── Strategy Objects:
│   ├── XComGameState_Objective (34f, 1,215l)
│   ├── XComGameState_DarkEvent (27f, 503l)
│   ├── XComGameState_Tech (19f, 420l)
│   ├── XComGameState_Reward (17f, 221l)
│   ├── XComGameState_StrategyCard (21f, 265l)
│   ├── XComGameState_MissionCalendar (21f, 653l)
│   └── XComGameState_CampaignSettings (33f, 400l)
│
├── Combat/Tactical Objects:
│   ├── XComGameState_Destructible (16f) → _InteractiveObject (37f)
│   ├── XComGameState_EvacZone (10f)
│   ├── XComGameState_LootDrop (22f)
│   ├── XComGameState_DestructionSphere (5f)
│   └── XComGameState_EnvironmentDamage (4f)
│
├── DLC Objects:
│   ├── XComGameState_AlienRulerManager (26f) [DLC_2]
│   ├── XComGameState_SparkManager (3f) [DLC_3]
│   └── XComGameState_HuntersLodgeManager (2f) [DLC_2]
│
├── XComGameState_Analytics (75f, 2,518l) — Game telemetry
├── XComGameState_LadderProgress (37f) — Challenge/Ladder mode
├── XComGameState_NarrativeManager (13f) — Dynamic narrative
├── XComGameState_XpManager (14f) — Experience system
└── ... (~20 more classes: TimerData, WorldEffects, etc.)
</code></pre>
<h3 id="gamestate-contexts-who-generates-changes">3.4 GameState Contexts (who generates changes)</h3>

<table>
<thead>
<tr>
<th>Context</th>
<th>Funcs</th>
<th>Lines</th>
<th>Purpose</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>XComGameStateContext_Ability</code></td>
<td>42</td>
<td>1,722</td>
<td><strong>Ability activation</strong> (most important)</td>
</tr>
<tr>
<td><code>XComGameStateContext_StrategyGameRule</code></td>
<td>29</td>
<td>1,592</td>
<td>Strategy rules (projects, time, etc.)</td>
</tr>
<tr>
<td><code>XComGameStateContext_HeadquartersOrder</code></td>
<td>30</td>
<td>1,291</td>
<td>Player orders at HQ</td>
</tr>
<tr>
<td><code>XComGameStateContext_TacticalGameRule</code></td>
<td>22</td>
<td>919</td>
<td>Tactical rules (turns, spawns, etc.)</td>
</tr>
<tr>
<td><code>XComGameStateContext_WillRoll</code></td>
<td>10</td>
<td>789</td>
<td>Will rolls (panic, etc.)</td>
</tr>
<tr>
<td><code>XComGameStateContext_Falling</code></td>
<td>5</td>
<td>385</td>
<td>Unit falls</td>
</tr>
<tr>
<td><code>XComGameStateContext_RevealAI</code></td>
<td>9</td>
<td>354</td>
<td>AI pod reveal</td>
</tr>
<tr>
<td><code>XComGameStateContext_ChangeContainer</code></td>
<td>7</td>
<td>73</td>
<td><strong>Generic changes</strong> (most used by mods)</td>
</tr>
<tr>
<td><code>XComGameStateContext_EffectRemoved</code></td>
<td>7</td>
<td>119</td>
<td>Effect removal</td>
</tr>
<tr>
<td><code>XComGameStateContext_AreaDamage</code></td>
<td>6</td>
<td>216</td>
<td>Area damage</td>
</tr>
<tr>
<td><code>XComGameStateContext_Kismet</code></td>
<td>11</td>
<td>192</td>
<td>Changes from Kismet/scripting</td>
</tr>
</tbody>
</table><h3 id="state-modification-pattern">3.5 State Modification Pattern</h3>
<pre class=" language-unrealscript"><code class="prism  language-unrealscript">// PATTERN 1: Create new change state
NewGameState = class'XComGameStateContext_ChangeContainer'.static.CreateChangeState("Reason");

// PATTERN 2: Get modifiable version
UnitState = XComGameState_Unit(NewGameState.ModifyStateObject(
    class'XComGameState_Unit', UnitRef.ObjectID));

// PATTERN 3: Modify
UnitState.SetCurrentStat(eStat_HP, NewHP);

// PATTERN 4: Submit
`GAMERULES.SubmitGameState(NewGameState);

// ALTERNATIVE PATTERN: Create new object in state
NewItem = XComGameState_Item(NewGameState.CreateNewStateObject(class'XComGameState_Item'));
</code></pre>
<h3 id="state-reading-pattern">3.6 State Reading Pattern</h3>
<pre class=" language-unrealscript"><code class="prism  language-unrealscript">// Get history
History = `XCOMHISTORY;  // class'XComGameStateHistory'.static.GetGameStateHistory()

// Get object by ID (MOST FREQUENT PATTERN - 1,214+ uses)
UnitState = XComGameState_Unit(History.GetGameStateForObjectID(ObjectID));

// Get global singleton (260 uses)
XComHQ = XComGameState_HeadquartersXCom(
    History.GetSingleGameStateObjectForClass(class'XComGameState_HeadquartersXCom'));

// Iterate over objects of a type
foreach History.IterateByClassType(class'XComGameState_Unit', UnitState) { ... }
</code></pre>
<hr>
<h2 id="tactical-combat-system">4. Tactical Combat System</h2>
<h3 id="combat-architecture">4.1 Combat Architecture</h3>
<pre><code>X2TacticalGameRuleset (150f, 5,891l) — Tactical game state machine
  │  73 states (State Machine) — turns, phases, AI, interrupts
  │
  ├── Abilities
  │   ├── X2AbilityTemplate (36f, 1,044l) — Ability definition
  │   ├── XComGameState_Ability (138f) — Ability instance on a unit
  │   ├── X2Ability_DefaultAbilitySet (72f, 3,740l) — Standard abilities
  │   ├── X2Ability_Chosen (75f, 2,930l) — Chosen abilities
  │   └── 134 total X2Ability_* classes
  │
  ├── Effects
  │   ├── X2Effect_Persistent (78f, 943l) — Base for lasting effects
  │   ├── X2Effect_ApplyWeaponDamage (16f, 1,709l) — Weapon damage
  │   └── 204 total X2Effect_* classes (118 persistent)
  │
  ├── Conditions
  │   ├── X2Condition (base, 45 subclasses)
  │   └── X2Condition_UnitProperty, _Visibility, _AbilityProperty, etc.
  │
  ├── Visualization Actions
  │   ├── X2Action (49f, 1,240l) — Base for visual actions
  │   ├── X2Action_ApplyWeaponDamageToUnit (30f, 1,313l) — Visual damage
  │   ├── X2Action_Fire (17f, 668l) — Firing
  │   ├── X2Action_Move (18f, 638l) — Movement
  │   └── 199 total X2Action_* classes (151 inherit X2Action)
  │
  ├── Targeting Methods
  │   ├── X2TargetingMethod (base, 13 subclasses in Engine)
  │   └── X2TargetingMethod_Grenade, _Cone, _OverTheShoulder, etc.
  │
  └── World Data
      ├── XComWorldData (163f, 1,255l) — Map tile data
      ├── XComGameState_BattleData — Current battle data
      └── X2TacticalGameRulesetDataStructures — 62 structs, 13 enums
</code></pre>
<h3 id="ability-flow-ability-pipeline">4.2 Ability Flow (Ability Pipeline)</h3>
<pre><code>1. AVAILABILITY: X2GameRuleset.GetGameRulesCache_Unit()
   → X2AbilityTemplate.CanAbilityBeActivated()
   → X2Condition[].MeetsCondition()      // All conditions must pass
   → X2AbilityCost[].CanAfford()          // Action cost, ammo, etc.

2. ACTIVATION: XComGameStateContext_Ability.ContextBuildGameState()
   → X2AbilityToHitCalc.GetHitChance()   // Hit probability calculation
   → X2AbilityTemplate.BuildNewGameState()// Generates the new GameState
   → X2Effect[].ApplyEffect()            // Applies effects to targets

3. VISUALIZATION: XComGameStateContext_Ability.ContextBuildVisualization()
   → X2AbilityTemplate.BuildVisualization()// Creates X2Actions
   → X2Action_ExitCover → X2Action_Fire → X2Action_ApplyWeaponDamage → ...
   → XComGameStateVisualizationMgr executes the chain

4. INTERRUPTIONS: The system supports interruptions (e.g., Overwatch)
   → eInterruptionStatus_Interrupt
   → New context from the interrupting ability
   → eInterruptionStatus_Resume (original ability continues)
</code></pre>
<h3 id="x2abilitytemplate-structure-the-most-complex-template">4.3 X2AbilityTemplate Structure (the most complex template)</h3>
<pre class=" language-unrealscript"><code class="prism  language-unrealscript">class X2AbilityTemplate extends X2DataTemplate;

// 13 delegates that define behavior:
delegate BuildNewGameStateDelegate;           // Creates the ability's GameState
delegate BuildInterruptGameStateDelegate;     // GameState if interrupted
delegate BuildVisualizationDelegate;          // Creates the visualization chain
delegate BuildVisualizationSyncDelegate;      // Visual synchronization
delegate OnSoldierAbilityPurchased;           // When ability is purchased
delegate ModifyNewContextDelegate;            // Modify context before creation
delegate CheckShooterConditionsDelegate;      // Shooter conditions
delegate CheckMultiTargetConditionsDelegate;  // Multi-target conditions
delegate MergeVisualizationDelegate;          // Visualization merging
delegate DamagePreviewDelegate;               // Damage preview
delegate PurePassiveCheckDelegate;            // Is it purely passive?
delegate ChosenTraitCheckDelegate;            // Is it a Chosen trait?
delegate WaypointCheckDelegate;               // Requires waypoints?

// Configurable components:
var array&lt;X2AbilityCost&gt; AbilityCosts;           // Costs
var array&lt;X2Condition&gt; AbilityShooterConditions;  // Shooter conditions
var array&lt;X2Condition&gt; AbilityTargetConditions;   // Target conditions
var array&lt;X2Effect&gt; AbilityTargetEffects;         // Effects on target
var array&lt;X2Effect&gt; AbilityMultiTargetEffects;    // Effects on multiple targets
var array&lt;X2Effect&gt; AbilityShooterEffects;        // Effects on shooter
var X2AbilityToHitCalc AbilityToHitCalc;          // Hit chance calculation
var X2AbilityTrigger AbilityTriggers;             // What triggers the ability
var X2AbilityTarget AbilityTargetStyle;           // How target is selected
var X2AbilityMultiTarget AbilityMultiTargetStyle; // Multi-targeting
</code></pre>
<h3 id="effects-system">4.4 Effects System</h3>
<p>The 204 <code>X2Effect_*</code> classes are grouped as:</p>

<table>
<thead>
<tr>
<th>Category</th>
<th>Examples</th>
<th>Count</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Damage</strong></td>
<td><code>ApplyWeaponDamage</code>, <code>ApplyDirectDamage</code></td>
<td>~20</td>
</tr>
<tr>
<td><strong>Stats</strong></td>
<td><code>PersistentStatChange</code>, <code>ModifyStats</code></td>
<td>~15</td>
</tr>
<tr>
<td><strong>Action</strong></td>
<td><code>GrantActionPoints</code>, <code>SetUnitValue</code></td>
<td>~15</td>
</tr>
<tr>
<td><strong>Control</strong></td>
<td><code>Stunned</code>, <code>Stasis</code>, <code>MindControl</code>, <code>Panicked</code></td>
<td>~10</td>
</tr>
<tr>
<td><strong>Spawn/Summon</strong></td>
<td><code>SpawnUnit</code>, <code>SpawnPsiZombie</code>, <code>SpawnCocoon</code></td>
<td>~8</td>
</tr>
<tr>
<td><strong>Movement</strong></td>
<td><code>Knockback</code>, <code>Teleport</code>, <code>AirdropCarryUnit</code></td>
<td>~8</td>
</tr>
<tr>
<td><strong>Visual/Audio</strong></td>
<td><code>PlayAnimation</code>, <code>Persistent (visual)</code></td>
<td>~10</td>
</tr>
<tr>
<td><strong>Status</strong></td>
<td><code>Burning</code>, <code>Poison</code>, <code>Bleeding</code>, <code>Freeze</code></td>
<td>~10</td>
</tr>
<tr>
<td><strong>Miscellaneous</strong></td>
<td>100+ specialized effects</td>
<td>~108</td>
</tr>
</tbody>
</table><hr>
<h2 id="strategic-layer">5. Strategic Layer</h2>
<h3 id="architecture">5.1 Architecture</h3>
<pre><code>X2StrategyGameRuleset — Strategic game rules
  │
  ├── Headquarters (Avenger)
  │   ├── XComGameState_HeadquartersXCom (331f, 9,576l) ★
  │   │   → Soldiers, inventory, projects, facilities
  │   ├── XComGameState_FacilityXCom (52f) → Facilities
  │   ├── XComGameState_StaffSlot (42f) → Staff slots
  │   └── XComGameState_HeadquartersProject (22f) → Projects (14 subclasses)
  │
  ├── Geoscape (World Map)
  │   ├── XComGameState_WorldRegion (93f, 2,306l) → Regions
  │   ├── XComGameState_MissionSite (79f) → Mission sites
  │   ├── XComGameState_CovertAction (102f, 2,588l) → Covert actions [WOTC]
  │   ├── XComGameState_PointOfInterest (41f) → Points of interest
  │   └── XComGameState_BlackMarket (42f) → Black market
  │
  ├── Enemies (Alien HQ)
  │   ├── XComGameState_HeadquartersAlien (129f, 3,721l)
  │   ├── XComGameState_AdventChosen (100f, 1,963l) [WOTC]
  │   ├── XComGameState_DarkEvent (27f, 503l)
  │   └── XComGameState_AlienRulerManager (26f) [DLC_2]
  │
  ├── Resistance
  │   ├── XComGameState_HeadquartersResistance (84f, 2,328l)
  │   ├── XComGameState_ResistanceFaction (94f, 1,464l) [WOTC]
  │   └── XComGameState_Haven (31f)
  │
  ├── Strategy Templates (46 classes)
  │   ├── X2StrategyElement_DefaultObjectives (199f, 4,513l)
  │   ├── X2StrategyElement_XpackResistanceActions (192f, 2,521l)
  │   ├── X2StrategyElement_DefaultRewards (133f)
  │   ├── X2StrategyElement_DefaultMissionSources (107f, 2,930l)
  │   └── X2StrategyElement_DefaultAlienAI (116f, 1,470l)
  │
  └── Data Structures
      └── X2StrategyGameRulesetDataStructures (116f, 3,349l)
          → 88 structs, 16 enums — all strategy types
</code></pre>
<h3 id="hq-project-types">5.2 HQ Project Types</h3>

<table>
<thead>
<tr>
<th>Project</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>_ProjectResearch</code></td>
<td>Technology research</td>
</tr>
<tr>
<td><code>_ProjectProvingGround</code></td>
<td>Proving Ground projects</td>
</tr>
<tr>
<td><code>_ProjectBuildFacility</code></td>
<td>Facility construction</td>
</tr>
<tr>
<td><code>_ProjectBuildItem</code></td>
<td>Item manufacturing</td>
</tr>
<tr>
<td><code>_ProjectClearRoom</code></td>
<td>Room clearing</td>
</tr>
<tr>
<td><code>_ProjectHealSoldier</code></td>
<td>Soldier healing</td>
</tr>
<tr>
<td><code>_ProjectHealSpark</code></td>
<td>SPARK repair [DLC_3]</td>
</tr>
<tr>
<td><code>_ProjectPsiTraining</code></td>
<td>Psionic training</td>
</tr>
<tr>
<td><code>_ProjectTrainRookie</code></td>
<td>Rookie training</td>
</tr>
<tr>
<td><code>_ProjectRecoverWill</code></td>
<td>Will recovery</td>
</tr>
<tr>
<td><code>_ProjectRespecSoldier</code></td>
<td>Ability respec</td>
</tr>
<tr>
<td><code>_ProjectBondSoldiers</code></td>
<td>Soldier bonding [WOTC]</td>
</tr>
<tr>
<td><code>_ProjectRemoveTraits</code></td>
<td>Negative trait removal</td>
</tr>
<tr>
<td><code>_ProjectUpgradeFacility</code></td>
<td>Facility upgrade</td>
</tr>
</tbody>
</table><h3 id="configuration-files-config-files">5.3 Configuration Files (Config Files)</h3>

<table>
<thead>
<tr>
<th>Config</th>
<th>Classes</th>
<th>Content</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>GameData</code></td>
<td>44</td>
<td>General game data, balance</td>
</tr>
<tr>
<td><code>GameCore</code></td>
<td>33</td>
<td>Core mechanics, stats, tiles</td>
</tr>
<tr>
<td><code>GameData_SoldierSkills</code></td>
<td>22</td>
<td>Soldier abilities</td>
</tr>
<tr>
<td><code>GameData_WeaponData</code></td>
<td>11</td>
<td>Weapon data</td>
</tr>
<tr>
<td><code>GameData_CharacterStats</code></td>
<td>5</td>
<td>Character statistics</td>
</tr>
<tr>
<td><code>GameBoard</code></td>
<td>4</td>
<td>Board/map data</td>
</tr>
<tr>
<td><code>Camera</code></td>
<td>2</td>
<td>Camera configuration</td>
</tr>
<tr>
<td><code>Ladder</code></td>
<td>2</td>
<td>Ladder mode</td>
</tr>
</tbody>
</table><hr>
<h2 id="artificial-intelligence-system">6. Artificial Intelligence System</h2>
<h3 id="ai-architecture">6.1 AI Architecture</h3>
<pre><code>XGAIPlayer (100f, 2,313l) — Main AI player
  │
  ├── XGAIBehavior (364f, 10,870l) ★ Largest AI class
  │   → 32 states, 13 structs
  │   → Behavior Tree evaluation, scoring, targeting
  │
  ├── Behavior Tree System
  │   ├── X2AIBTBehaviorTree (35f, 518l) — BT manager
  │   ├── X2AIBTBehavior (15f) — Base node
  │   ├── X2AIBTComposite (15f) — Composite nodes (selector/sequence)
  │   ├── X2AIBTDecorator (14f) — Decorators
  │   ├── X2AIBTLeafNode (11f) — Leaf nodes
  │   │   ├── X2AIBTDefaultConditions (153f, 2,737l) — All BT conditions
  │   │   └── X2AIBTDefaultActions (112f, 1,778l) — All BT actions
  │   └── DLC extensions: X2AIBT_DLC_60Actions/Conditions, _DLC_90Actions/Conditions
  │
  ├── Job System
  │   └── X2AIJobManager (29f, 721l) — Job assignment to pods
  │
  └── AI State (GameState)
      ├── XComGameState_AIGroup (46f, 1,850l)
      ├── XComGameState_AIPlayerData (35f, 990l)
      ├── XComGameState_AIUnitData (33f, 1,240l)
      ├── XComGameState_AIBlackboard (10f, 250l)
      └── XComGameState_AIReinforcementSpawner (17f, 931l)
</code></pre>
<h3 id="behavior-tree-—-evaluation-flow">6.2 Behavior Tree — Evaluation Flow</h3>
<pre><code>XGAIBehavior.RunBehaviorTree()
  → X2AIBTBehaviorTree.FindBehaviorTreeRoot()
  → X2AIBTComposite.Run() — Evaluates nodes recursively
     ├── X2AIBTDefaultConditions.FindBTConditionDelegate()
     │   → 153 condition functions (HasTarget, IsInCover, etc.)
     └── X2AIBTDefaultActions.FindBTActionDelegate()
         → 112 action functions (SelectAbility, FindTarget, etc.)
</code></pre>
<h3 id="ai-logging-macros">6.3 AI Logging Macros</h3>
<pre class=" language-unrealscript"><code class="prism  language-unrealscript">`LOGAI(msg)           // General AI log
`LOGAIBT(msg)         // Behavior Tree log
`LOGAIActions(msg)    // AI actions log
`LogConcealment(msg)  // Concealment/detection log
</code></pre>
<hr>
<h2 id="ui-system">7. UI System</h2>
<h3 id="architecture-1">7.1 Architecture</h3>
<pre><code>UIScreen (137 subclasses) — Full screen
  │
  ├── UIPanel (128 subclasses) — Base component/widget
  │   ├── UIList, UIButton, UIText, UIImage
  │   ├── UINavigationHelp — Navigation help
  │   └── UITooltip (13 subclasses)
  │
  ├── UIScreenStack — Screen stack (Stack pattern)
  │
  ├── Tactical UI:
  │   ├── UITacticalHUD (main tactical HUD)
  │   ├── UITacticalHUD_ShotHUD (shot panel)
  │   ├── UITacticalHUD_AbilityContainer (ability bar)
  │   ├── UITacticalHUD_SoldierInfo (soldier info)
  │   └── UIUnitFlag (flag above unit)
  │
  ├── Strategy UI:
  │   ├── UIAlert (167f, 5,801l) — Alert system (largest UI class)
  │   ├── UIArmory_* — Armory (equipment, promotion)
  │   ├── UIFacility_* (19 subclasses) — Facility screens
  │   ├── UIResearchArchives, UIBuildFacilities, etc.
  │   └── UIStrategyMap, UIStrategyMapItem (20 subclasses)
  │
  ├── UIMission (16 subclasses) — Mission briefings
  │   └── UIMission_ChosenAmbush, _Council, _GOps, _Retaliation, etc.
  │
  ├── UIScreenListener (61+ subclasses) — Screen hooks
  │
  └── Helpers:
      ├── UIUtilities (93 refs) — General utilities
      ├── UIUtilities_Input (284 refs) — Input handling ★ most referenced
      ├── UIUtilities_Text (220 refs) — Text formatting
      ├── UIUtilities_Strategy (149 refs) — Strategy utils
      └── UIUtilities_Image (96 refs) — Image handling
</code></pre>
<h3 id="largest-ui-classes">7.2 Largest UI Classes</h3>

<table>
<thead>
<tr>
<th>Class</th>
<th>Funcs</th>
<th>Lines</th>
<th>Role</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>UIAlert</code></td>
<td>167</td>
<td>5,801</td>
<td>Pop-up/alert system</td>
</tr>
<tr>
<td><code>UIOptionsPCScreen</code></td>
<td>166</td>
<td>3,252</td>
<td>Options screen</td>
</tr>
<tr>
<td><code>UIPhotoboothBase</code></td>
<td>163</td>
<td>2,833</td>
<td>Photobooth base</td>
</tr>
<tr>
<td><code>UIMPShell_Lobby</code></td>
<td>110</td>
<td>2,184</td>
<td>Multiplayer lobby</td>
</tr>
<tr>
<td><code>UIChallengeMode_SquadSelect</code></td>
<td>103</td>
<td>2,529</td>
<td>Challenge mode</td>
</tr>
<tr>
<td><code>UITLE_SkirmishModeMenu</code></td>
<td>102</td>
<td>3,349</td>
<td>Skirmish menu (TLE)</td>
</tr>
<tr>
<td><code>XComHQPresentationLayer</code></td>
<td>341</td>
<td>6,014</td>
<td>HQ presentation layer</td>
</tr>
<tr>
<td><code>XComPresentationLayerBase</code></td>
<td>221</td>
<td>3,056</td>
<td>Base presentation layer</td>
</tr>
</tbody>
</table><hr>
<h2 id="event-system">8. Event System</h2>
<h3 id="event-manager-architecture">8.1 Event Manager Architecture</h3>
<pre class=" language-unrealscript"><code class="prism  language-unrealscript">class X2EventManager extends Object native(Core);

// Global access singleton
`XEVENTMGR  // → class'X2EventManager'.static.GetEventManager()

// Event delegate signature:
delegate EventListenerReturn OnEventDelegate(
    Object EventData,       // Event data
    Object EventSource,     // Event source
    XComGameState GameState,// Current state
    Name EventID,           // Event name
    Object CallbackData     // Optional extra data
);
</code></pre>
<h3 id="deferral-types-when-notification-occurs">8.2 Deferral Types (when notification occurs)</h3>

<table>
<thead>
<tr>
<th>Deferral</th>
<th>When it executes</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>ELD_Immediate</code></td>
<td>Immediately when the event fires</td>
</tr>
<tr>
<td><code>ELD_PreStateSubmitted</code></td>
<td>Just before submitting to history</td>
</tr>
<tr>
<td><code>ELD_OnStateSubmitted</code></td>
<td>After submitting to history</td>
</tr>
<tr>
<td><code>ELD_OnVisualizationBlockStarted</code></td>
<td>When visualization begins</td>
</tr>
<tr>
<td><code>ELD_OnVisualizationBlockCompleted</code></td>
<td>When visualization completes</td>
</tr>
</tbody>
</table><h3 id="listener-return-values">8.3 Listener Return Values</h3>

<table>
<thead>
<tr>
<th>Return</th>
<th>Behavior</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>ELR_NoInterrupt</code></td>
<td>Continue normally</td>
</tr>
<tr>
<td><code>ELR_InterruptEvent</code></td>
<td>Interrupt the event (other listeners still execute)</td>
</tr>
<tr>
<td><code>ELR_InterruptListeners</code></td>
<td>Do not execute more listeners (event is NOT interrupted)</td>
</tr>
<tr>
<td><code>ELR_InterruptEventAndListeners</code></td>
<td>Interrupt everything</td>
</tr>
</tbody>
</table><h3 id="typical-usage">8.4 Typical Usage</h3>
<pre class=" language-unrealscript"><code class="prism  language-unrealscript">// REGISTRATION:
EventMgr = `XEVENTMGR;
EventMgr.RegisterForEvent(SelfObj, 'AbilityActivated', OnAbilityActivated, 
    ELD_OnStateSubmitted, /*Priority*/50);

// TRIGGER:
EventMgr.TriggerEvent('AbilityActivated', AbilityState, SourceUnit, NewGameState);

// HANDLER:
static function EventListenerReturn OnAbilityActivated(
    Object EventData, Object EventSource, XComGameState GameState, 
    Name EventID, Object CallbackData)
{
    // Process the event...
    return ELR_NoInterrupt;
}
</code></pre>
<hr>
<h2 id="global-macro-system-.uci">9. Global Macro System (.uci)</h2>
<h3 id="macro-files">9.1 Macro Files</h3>

<table>
<thead>
<tr>
<th>File</th>
<th>Purpose</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>Core/Globals.uci</code></td>
<td><strong>Fundamental engine and game macros</strong> (~300 lines)</td>
</tr>
<tr>
<td><code>extra_globals.uci</code></td>
<td>LWOTC macros (debugging, managers)</td>
</tr>
<tr>
<td><code>XComGame/XComOnlineConstants.uci</code></td>
<td>Online constants</td>
</tr>
<tr>
<td><code>Engine/Classes/PixelFormatEnum.uci</code></td>
<td>Pixel formats</td>
</tr>
<tr>
<td><code>Engine/Classes/UIDev.uci</code></td>
<td>UI development</td>
</tr>
<tr>
<td><code>MCM_API_*.uci</code></td>
<td>Mod Config Menu API</td>
</tr>
<tr>
<td><code>LW_*.uci</code></td>
<td>LWOTC mod logging/debug</td>
</tr>
</tbody>
</table><h3 id="global-access-macros-coreglobals.uci-—-most-important">9.2 Global Access Macros (Core/Globals.uci) — Most Important</h3>
<h4 id="gamestatehistory-access">GameState/History Access</h4>

<table>
<thead>
<tr>
<th>Macro</th>
<th>Expansion</th>
<th>Usage</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>`XCOMHISTORY</code> | <code>class'XComGameStateHistory'.static.GetGameStateHistory()</code></td>
<td>Access history</td>
<td></td>
</tr>
<tr>
<td><code>`XEVENTMGR</code> | <code>class'X2EventManager'.static.GetEventManager()</code></td>
<td>Event manager</td>
<td></td>
</tr>
<tr>
<td><code>`GAMERULES</code> | <code>XComGameInfo(...).GameRuleset</code></td>
<td>Game ruleset</td>
<td></td>
</tr>
<tr>
<td><code>`TACTICALRULES</code> | <code>X2TacticalGameRuleset(</code>GAMERULES)`</td>
<td>Tactical rules</td>
<td></td>
</tr>
<tr>
<td><code>`STRATEGYRULES</code> | <code>X2StrategyGameRuleset(</code>GAMERULES)`</td>
<td>Strategy rules</td>
<td></td>
</tr>
<tr>
<td><code>`XCOMHQ</code> | <code>class'UIUtilities_Strategy'.static.GetXComHQ()</code></td>
<td>XCOM HQ</td>
<td></td>
</tr>
</tbody>
</table><h4 id="world-singleton-access">World Singleton Access</h4>

<table>
<thead>
<tr>
<th>Macro</th>
<th>Expansion</th>
<th>Usage</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>`XWORLD</code> | <code>class'XComWorldData'.static.GetWorldData()</code></td>
<td>World/tile data</td>
<td></td>
</tr>
<tr>
<td><code>`XCOMGRI</code> | <code>XComGameReplicationInfo(...)</code></td>
<td>Game Replication Info</td>
<td></td>
</tr>
<tr>
<td><code>`TACTICALGRI</code> | <code>XComTacticalGRI(</code>XCOMGRI)`</td>
<td>Tactical GRI</td>
<td></td>
</tr>
<tr>
<td><code>`BATTLE</code> | <code>XComTacticalGRI(...).m_kBattle</code></td>
<td>Current battle</td>
<td></td>
</tr>
<tr>
<td><code>`XCOMVISUALIZATIONMGR</code> | <code>XComGameReplicationInfo(...).VisualizationMgr</code></td>
<td>Visualization manager</td>
<td></td>
</tr>
<tr>
<td><code>`XWORLDINFO</code> | <code>class'Engine'.static.GetCurrentWorldInfo()</code></td>
<td>WorldInfo</td>
<td></td>
</tr>
</tbody>
</table><h4 id="ui-and-presentation">UI and Presentation</h4>

<table>
<thead>
<tr>
<th>Macro</th>
<th>Expansion</th>
<th>Usage</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>`HQPRES</code> | <code>class'XComEngine'.static.GetHQPres()</code></td>
<td>HQ Presentation Layer</td>
<td></td>
</tr>
<tr>
<td><code>`PRES</code> | <code>XComPresentationLayer(...)</code></td>
<td>Tactical Presentation</td>
<td></td>
</tr>
<tr>
<td><code>`PRESBASE</code> | <code>XComPlayerController(...).Pres</code></td>
<td>Base Presentation</td>
<td></td>
</tr>
<tr>
<td><code>`SCREENSTACK</code> | <code>...Pres.ScreenStack</code></td>
<td>Screen stack</td>
<td></td>
</tr>
<tr>
<td><code>`TOOLTIPMGR</code> | <code>...Pres.m_kTooltipMgr</code></td>
<td>Tooltip manager</td>
<td></td>
</tr>
<tr>
<td><code>`ISCONTROLLERACTIVE</code> | <code>...IsMouseActive() == false</code></td>
<td>Using gamepad?</td>
<td></td>
</tr>
</tbody>
</table><h4 id="ai-and-managers">AI and Managers</h4>

<table>
<thead>
<tr>
<th>Macro</th>
<th>Expansion</th>
<th>Usage</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>`SPAWNMGR</code> | <code>class'XComAISpawnManager'.static.GetSpawnManager()</code></td>
<td>Spawn manager</td>
<td></td>
</tr>
<tr>
<td><code>`AIJOBMGR</code> | <code>class'X2AIJobManager'.static.GetAIJobManager()</code></td>
<td>AI Job manager</td>
<td></td>
</tr>
<tr>
<td><code>`BEHAVIORTREEMGR</code> | <code>class'X2AIBTBehaviorTree'.static.GetBehaviorTreeManager()</code></td>
<td>BT manager</td>
<td></td>
</tr>
<tr>
<td><code>`CHEATMGR</code> | <code>XComTacticalCheatManager(...)</code></td>
<td>Cheat manager</td>
<td></td>
</tr>
<tr>
<td><code>`PARCELMGR</code> | <code>XComParcelManager(...)</code></td>
<td>Parcel/map manager</td>
<td></td>
</tr>
<tr>
<td><code>`TACTICALMISSIONMGR</code> | <code>XComTacticalMissionManager(...)</code></td>
<td>Mission manager</td>
<td></td>
</tr>
</tbody>
</table><h4 id="conversion-utilities">Conversion Utilities</h4>

<table>
<thead>
<tr>
<th>Macro</th>
<th>Formula</th>
<th>Example</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>`METERSTOUNITS(x)</code> | <code>x * 64</code></td>
<td>Meters to Unreal units</td>
<td></td>
</tr>
<tr>
<td><code>`UNITSTOMETERS(x)</code> | <code>x / 64</code></td>
<td>Units to meters</td>
<td></td>
</tr>
<tr>
<td><code>`UNITSTOTILES(x)</code> | <code>x / 96</code></td>
<td>Units to tiles</td>
<td></td>
</tr>
<tr>
<td><code>`TILESTOUNITS(x)</code> | <code>x * 96</code></td>
<td>Tiles to units</td>
<td></td>
</tr>
<tr>
<td><code>`METERSTOTILES(x)</code> | <code>x / 1.5f</code></td>
<td>Meters to tiles</td>
<td></td>
</tr>
</tbody>
</table><h4 id="difficulty">Difficulty</h4>

<table>
<thead>
<tr>
<th>Macro</th>
<th>Usage</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>`CampaignDifficultySetting</code></td>
<td>Campaign difficulty level</td>
</tr>
<tr>
<td><code>`TacticalDifficultySetting</code></td>
<td>Tactical difficulty</td>
</tr>
<tr>
<td><code>`StrategyDifficultySetting</code></td>
<td>Strategy difficulty</td>
</tr>
<tr>
<td><code>`ScaleTacticalArrayInt(x)</code></td>
<td>Scale array by tactical difficulty</td>
</tr>
<tr>
<td><code>`SecondWaveEnabled(x)</code></td>
<td>Is Second Wave option active?</td>
</tr>
</tbody>
</table><h4 id="templates">Templates</h4>

<table>
<thead>
<tr>
<th>Macro</th>
<th>Usage</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>`CREATE_X2TEMPLATE(Class, Obj, Name)</code></td>
<td>Create any template</td>
</tr>
<tr>
<td><code>`CREATE_X2ABILITY_TEMPLATE(T, N)</code></td>
<td>Create AbilityTemplate</td>
</tr>
<tr>
<td><code>`CREATE_X2CHARACTER_TEMPLATE(T, N)</code></td>
<td>Create CharacterTemplate</td>
</tr>
</tbody>
</table><h4 id="debugginglogging">Debugging/Logging</h4>

<table>
<thead>
<tr>
<th>Macro</th>
<th>Usage</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>`RedScreen(Error)</code></td>
<td>Display error on red screen</td>
</tr>
<tr>
<td><code>`COMBATLOG(msg)</code></td>
<td>Combat log</td>
</tr>
<tr>
<td><code>`LOGAI(msg)</code></td>
<td>AI log</td>
</tr>
<tr>
<td><code>`LOGAIBT(msg)</code></td>
<td>Behavior Tree log</td>
</tr>
<tr>
<td><code>`SYNC_RAND(x)</code></td>
<td>Synchronized random (for replay/MP)</td>
</tr>
</tbody>
</table><hr>
<h2 id="template-system-and-data-driven-design">10. Template System and Data-Driven Design</h2>
<h3 id="template-hierarchy">10.1 Template Hierarchy</h3>
<pre><code>X2DataTemplate — Base of all templates
├── X2AbilityTemplate (36f, 1,044l) — Abilities
├── X2CharacterTemplate — Characters/units
├── X2ItemTemplate → X2EquipmentTemplate → X2WeaponTemplate, X2ArmorTemplate
├── X2SitRepTemplate — Mission SitReps
├── X2HackRewardTemplate — Hack rewards
├── X2SitRepEffectTemplate — SitRep effects
└── X2StrategyElementTemplate — Strategy templates
    ├── X2MissionSourceTemplate (15 delegates!)
    ├── X2MissionFlavorTemplate
    ├── X2FacilityTemplate (11 delegates)
    ├── X2DarkEventTemplate
    ├── X2RewardTemplate (14 delegates)
    ├── X2StaffSlotTemplate (13 delegates)
    ├── X2X2AdventChosenTemplate
    ├── X2CountryTemplate, X2ContinentTemplate, X2RegionTemplate
    ├── X2TechTemplate, X2ObjectiveTemplate
    └── ... (33 total subclasses)
</code></pre>
<h3 id="template-managers">10.2 Template Managers</h3>
<p>Each template type has a singleton manager for accessing definitions:</p>

<table>
<thead>
<tr>
<th>Manager</th>
<th>Templates managed</th>
<th>Refs</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>X2AbilityTemplateManager</code></td>
<td>Abilities</td>
<td>131</td>
</tr>
<tr>
<td><code>X2CharacterTemplateManager</code></td>
<td>Characters</td>
<td>106</td>
</tr>
<tr>
<td><code>X2ItemTemplateManager</code></td>
<td>Items/weapons</td>
<td>74</td>
</tr>
<tr>
<td><code>X2StrategyElementTemplateManager</code></td>
<td>Strategy</td>
<td>76</td>
</tr>
<tr>
<td><code>X2SitRepTemplateManager</code></td>
<td>SitReps</td>
<td>~10</td>
</tr>
</tbody>
</table><h3 id="data-sets-bulk-data-definition">10.3 Data Sets (Bulk data definition)</h3>

<table>
<thead>
<tr>
<th>Class</th>
<th>Funcs</th>
<th>Lines</th>
<th>What it defines</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>X2Character_DefaultCharacters</code></td>
<td>119</td>
<td>6,312</td>
<td><strong>ALL</strong> base characters</td>
</tr>
<tr>
<td><code>X2Item_DefaultWeapons</code></td>
<td>95</td>
<td>4,574</td>
<td>All base weapons</td>
</tr>
<tr>
<td><code>X2Item_XpackWeapons</code></td>
<td>76</td>
<td>3,592</td>
<td>WOTC weapons</td>
</tr>
<tr>
<td><code>X2Ability_DefaultAbilitySet</code></td>
<td>72</td>
<td>3,740</td>
<td>Standard abilities</td>
</tr>
<tr>
<td><code>X2Ability_Chosen</code></td>
<td>75</td>
<td>2,930</td>
<td>Chosen abilities</td>
</tr>
<tr>
<td><code>X2StrategyElement_DefaultObjectives</code></td>
<td>199</td>
<td>4,513</td>
<td>All objectives</td>
</tr>
<tr>
<td><code>X2StrategyElement_DefaultAlienAI</code></td>
<td>116</td>
<td>1,470</td>
<td>Base alien AI</td>
</tr>
<tr>
<td><code>X2DynamicNarrative_DefaultDynamicNarratives</code></td>
<td>142</td>
<td>1,982</td>
<td>Dynamic narrative</td>
</tr>
</tbody>
</table><h3 id="delegate-usage-pattern-in-templates">10.4 Delegate Usage Pattern in Templates</h3>
<pre class=" language-unrealscript"><code class="prism  language-unrealscript">// X2MissionSourceTemplate — 15 delegates:
delegate OnTriadSuccessDelegate;
delegate OnTriadFailureDelegate;
delegate OnSuccessDelegate;
delegate OnFailureDelegate;
delegate OnExpireDelegate;
// ...

// X2RewardTemplate — 14 delegates:
delegate IsRewardAvailableDelegate;
delegate IsRewardNeededDelegate;
delegate GenerateRewardDelegate;
delegate SetRewardDelegate;
delegate GiveRewardDelegate;
// ...

// CHItemSlot (Highlander) — 14 delegates:
delegate CanAddItemToSlotFn;
delegate UnitHasSlotFn;
delegate GetPriorityFn;
delegate GetMaxItemCountFn;
delegate AddItemToSlotFn;
// ...
</code></pre>
<hr>
<h2 id="dlcs-and-expansions">11. DLCs and Expansions</h2>
<h3 id="dlc_1-anarchys-children">11.1 DLC_1: Anarchy’s Children</h3>
<ul>
<li><strong>2 classes</strong> — Purely cosmetic (customization)</li>
<li><code>UIScreenListener_UICustomize</code>, <code>X2DownloadableContentInfo_DLC_1</code></li>
</ul>
<h3 id="dlc_2-alien-hunters-59-classes">11.2 DLC_2: Alien Hunters (59 classes)</h3>

<table>
<thead>
<tr>
<th>System</th>
<th>Main Classes</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Alien Rulers</strong></td>
<td><code>XComGameState_AlienRulerManager</code> — ruler management</td>
</tr>
<tr>
<td><strong>Ruler Abilities</strong></td>
<td><code>X2Ability_DLC_Day60AlienRulers</code>, <code>_ArchonKing</code>, <code>_ViperKing</code>, <code>_BerserkerQueen</code></td>
</tr>
<tr>
<td><strong>Ruler Actions</strong></td>
<td><code>X2Effect_DLC_2RulerActionPoint</code> — ruler action per turn</td>
</tr>
<tr>
<td><strong>Items</strong></td>
<td><code>X2Item_DLC_Day60Weapons/Armors/Grenades/Schematics</code> — Icarus, Bolt Caster, etc.</td>
</tr>
<tr>
<td><strong>Freeze Effect</strong></td>
<td><code>X2Effect_DLC_Day60Freeze</code> (14f) — freeze effect</td>
</tr>
<tr>
<td><strong>Hunter’s Lodge</strong></td>
<td><code>UIFacility_HuntersLodge</code>, <code>XComGameState_HuntersLodgeManager</code></td>
</tr>
<tr>
<td><strong>AI</strong></td>
<td><code>X2AIBT_DLC_60Actions</code> (8f), <code>X2AIBT_DLC_60Conditions</code> (13f)</td>
</tr>
<tr>
<td><strong>Helpers</strong></td>
<td><code>X2Helpers_DLC_Day60</code> (36f, 980l) — shared logic</td>
</tr>
</tbody>
</table><h3 id="dlc_3-shens-last-gift--spark-57-classes">11.3 DLC_3: Shen’s Last Gift / SPARK (57 classes)</h3>

<table>
<thead>
<tr>
<th>System</th>
<th>Main Classes</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>SPARK Units</strong></td>
<td><code>X2Character_DLC_Day90Characters</code> (14f, 868l)</td>
</tr>
<tr>
<td><strong>SPARK Abilities</strong></td>
<td><code>X2Ability_SparkAbilitySet</code> (42f, 1,898l) — Overdrive, Strike, Sacrifice, etc.</td>
</tr>
<tr>
<td><strong>SPARK Healing</strong></td>
<td><code>XComGameState_HeadquartersProjectHealSpark</code></td>
</tr>
<tr>
<td><strong>SPARK Manager</strong></td>
<td><code>XComGameState_SparkManager</code></td>
</tr>
<tr>
<td><strong>Effects</strong></td>
<td><code>X2Effect_DLC_3AbsorptionField</code>, <code>_Overdrive</code>, <code>_Rainmaker</code>, <code>_SacrificeShield</code></td>
</tr>
<tr>
<td><strong>Customization</strong></td>
<td><code>UICustomize_SparkBody/Head/Menu/Props/Weapon</code> (6 classes)</td>
</tr>
<tr>
<td><strong>AI</strong></td>
<td><code>X2AIBT_DLC_90Actions</code> (4f), <code>X2AIBT_DLC_90Conditions</code> (6f)</td>
</tr>
<tr>
<td><strong>Lost Towers</strong></td>
<td><code>XComGameState_MissionSiteLostTowers</code>, narrative, mission sources</td>
</tr>
</tbody>
</table><h3 id="tle-tactical-legacy-pack-11-classes">11.4 TLE: Tactical Legacy Pack (11 classes)</h3>
<ul>
<li>Legacy weapons: <code>X2Item_TLE_Weapons</code> (34f, 1,179l)</li>
<li>Legacy armor: <code>X2Item_TLE_Armor</code> (15f, 452l)</li>
<li>TLE characters: <code>X2Characters_TLE_Characters</code> (18f, 1,309l)</li>
<li>Narrative: <code>X2MissionNarrative_DLC_TLE</code> (28f, 847l)</li>
<li>Skirmish mode: <code>UITLE_SkirmishModeMenu</code> (102f, 3,349l)</li>
</ul>
<hr>
<h2 id="community-highlander">12. Community Highlander</h2>
<h3 id="purpose">12.1 Purpose</h3>
<p>The <strong>X2WOTCCommunityHighlander</strong> is a community mod that exposes hooks and extension points in the base game to facilitate modding. It acts as an abstraction layer between the base game and mods.</p>
<h3 id="classes-9-classes-hooksversion-only">12.2 Classes (9 classes, hooks/version only)</h3>

<table>
<thead>
<tr>
<th>Class</th>
<th>Purpose</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>X2DownloadableContentInfo_X2WOTCCommunityHighlander</code></td>
<td>Entry point, component validation</td>
</tr>
<tr>
<td><code>X2WOTCCH_Components</code></td>
<td>HL component versioning system</td>
</tr>
<tr>
<td><code>X2WOTCCH_ModDependencies</code></td>
<td>Mod dependency verification</td>
</tr>
<tr>
<td><code>X2WOTCCH_UIScreenListener_ShellPopup</code></td>
<td>Dependency warning popups</td>
</tr>
<tr>
<td><code>X2WOTCCH_UIScreenListener_ShellSplash</code></td>
<td>Version display in menu</td>
</tr>
<tr>
<td><code>X2WOTCCH_UIScreenListener_Shell_DLCIntro</code></td>
<td>DLC2 intro with HL</td>
</tr>
<tr>
<td><code>X2WOTCCH_DialogCallbackData</code></td>
<td>Dialog callbacks</td>
</tr>
<tr>
<td><code>CHX2WOTCCHVersion</code></td>
<td>HL version</td>
</tr>
<tr>
<td><code>X2WOTCCH_CHXComGameVersion</code></td>
<td>Game version</td>
</tr>
</tbody>
</table><h3 id="hl-classes-integrated-in-xcomgame">12.3 HL Classes Integrated in XComGame</h3>
<p>The Highlander <strong>modifies</strong> classes within <code>XComGame</code> (visible as <code>CHHelpers</code>, <code>CHItemSlot</code>, <code>CHEventListenerTemplate</code>, etc. in the code). These are not separate classes but extensions compiled within the XComGame package.</p>
<ul>
<li><code>CHHelpers</code> — 63 references in the codebase (modding utilities)</li>
<li><code>CHItemSlot</code> — 14 delegates for custom item slots</li>
<li><code>CHDLCHookManager</code> — DLC hook manager (<code>`DLCHOOKMGR</code>)</li>
<li><code>CHEventListenerTemplate</code> — Template for HL event listeners</li>
</ul>
<hr>
<h2 id="engine-—-fundamental-classes">13. Engine — Fundamental Classes</h2>
<h3 id="core-11-classes">13.1 Core (11 classes)</h3>

<table>
<thead>
<tr>
<th>Class</th>
<th>Funcs</th>
<th>Purpose</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>Object</code></td>
<td>183</td>
<td><strong>Root of everything</strong> — 53 structs, 12 enums, 94 native funcs</td>
</tr>
<tr>
<td><code>Field</code></td>
<td>0</td>
<td>Reflection: class field</td>
</tr>
<tr>
<td><code>Struct/State/Function/Enum/Const/Property</code></td>
<td>0</td>
<td>Reflection types</td>
</tr>
<tr>
<td><code>Package</code></td>
<td>0</td>
<td>Content packages</td>
</tr>
<tr>
<td><code>Component</code></td>
<td>0</td>
<td>Component base</td>
</tr>
<tr>
<td><code>DistributionFloat/Vector</code></td>
<td>0</td>
<td>Mathematical distributions</td>
</tr>
<tr>
<td><code>Commandlet</code></td>
<td>2</td>
<td>Command-line commands</td>
</tr>
</tbody>
</table><h3 id="engine-—-top-20-by-relevance">13.2 Engine — Top 20 by Relevance</h3>

<table>
<thead>
<tr>
<th>Class</th>
<th>Funcs</th>
<th>Lines</th>
<th>Purpose</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>Actor</code></td>
<td>227</td>
<td>4,503</td>
<td><strong>Base of everything in the world</strong> — 21 structs, 11 enums</td>
</tr>
<tr>
<td><code>PlayerController</code></td>
<td>366</td>
<td>8,841</td>
<td>Player control</td>
</tr>
<tr>
<td><code>Pawn</code></td>
<td>148</td>
<td>3,439</td>
<td>Controllable entities</td>
</tr>
<tr>
<td><code>GameInfo</code></td>
<td>132</td>
<td>3,751</td>
<td>Base game rules</td>
</tr>
<tr>
<td><code>WorldInfo</code></td>
<td>69</td>
<td>2,672</td>
<td>Current world info — 18 structs</td>
</tr>
<tr>
<td><code>SkeletalMeshComponent</code></td>
<td>124</td>
<td>1,753</td>
<td>Animated meshes — 9 enums</td>
</tr>
<tr>
<td><code>Engine</code></td>
<td>81</td>
<td>984</td>
<td>Main engine</td>
</tr>
<tr>
<td><code>Canvas</code></td>
<td>62</td>
<td>550</td>
<td>2D rendering</td>
</tr>
<tr>
<td><code>Camera</code></td>
<td>27</td>
<td>1,232</td>
<td>Camera system</td>
</tr>
<tr>
<td><code>NavigationPoint</code></td>
<td>20</td>
<td>416</td>
<td>Pathfinding navigation</td>
</tr>
</tbody>
</table><h3 id="engine-categories-1234-classes">13.3 Engine Categories (1,234 classes)</h3>

<table>
<thead>
<tr>
<th>Category</th>
<th>Classes</th>
<th>Examples</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Particles</strong></td>
<td>183</td>
<td>ParticleModule*, ParticleSystemComponent</td>
</tr>
<tr>
<td><strong>Kismet/Sequence</strong></td>
<td>168</td>
<td>SequenceAction*, SequenceEvent*, SequenceCondition*</td>
</tr>
<tr>
<td><strong>Materials</strong></td>
<td>167</td>
<td>MaterialExpression*, Material, MaterialInstance</td>
</tr>
<tr>
<td><strong>Actors</strong></td>
<td>140</td>
<td>Light, StaticMeshActor, Trigger, PhysicsVolume</td>
</tr>
<tr>
<td><strong>Components</strong></td>
<td>97</td>
<td>MeshComponent, AudioComponent, DecalComponent</td>
</tr>
<tr>
<td><strong>Interp/Matinee</strong></td>
<td>82</td>
<td>InterpTrack*, InterpTrackInst*, Matinee*</td>
</tr>
<tr>
<td><strong>Animation</strong></td>
<td>71</td>
<td>AnimNode*, AnimNotify*, SkeletalMeshSocket</td>
</tr>
<tr>
<td><strong>Volumes/Terrain</strong></td>
<td>53</td>
<td>Volume*, PostProcessVolume, Terrain</td>
</tr>
<tr>
<td><strong>Lights</strong></td>
<td>51</td>
<td>PointLight, SpotLight, DirectionalLight</td>
</tr>
<tr>
<td><strong>Sound</strong></td>
<td>48</td>
<td>SoundNode*, AmbientSound, SoundCue</td>
</tr>
<tr>
<td><strong>Physics</strong></td>
<td>48</td>
<td>RB_*, PhysXDestructible, KActor</td>
</tr>
<tr>
<td><strong>Rendering</strong></td>
<td>37</td>
<td>Texture*, Canvas, SceneCapture*</td>
</tr>
<tr>
<td><strong>Camera</strong></td>
<td>26</td>
<td>Camera, CameraActor, CameraAnim</td>
</tr>
</tbody>
</table><h3 id="native-functions">13.4 Native Functions</h3>
<p><strong>4,092 native functions</strong> in the base game (implemented in C++, exposed to UnrealScript).</p>

<table>
<thead>
<tr>
<th>Class</th>
<th>Native</th>
<th>Domain</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>XComWorldData</code></td>
<td>161</td>
<td>World/tile data (pathfinding, LOS, cover)</td>
</tr>
<tr>
<td><code>Actor</code></td>
<td>123</td>
<td>Transforms, collisions, lifecycle</td>
</tr>
<tr>
<td><code>SkeletalMeshComponent</code></td>
<td>114</td>
<td>Animation, bones, morphs</td>
</tr>
<tr>
<td><code>XComGameState_Unit</code></td>
<td>114</td>
<td>Stats, visibility, combat</td>
</tr>
<tr>
<td><code>OnlineSubsystemSteamworks</code></td>
<td>113</td>
<td>Steam integration</td>
</tr>
<tr>
<td><code>Object</code></td>
<td>94</td>
<td>Reflection, logging, math</td>
</tr>
<tr>
<td><code>XComEngine</code></td>
<td>70</td>
<td>XCom extended engine</td>
</tr>
<tr>
<td><code>X2FiraxisLiveClient</code></td>
<td>57</td>
<td>Firaxis Live (online services)</td>
</tr>
<tr>
<td><code>ParticleSystemComponent</code></td>
<td>56</td>
<td>Particles</td>
</tr>
<tr>
<td><code>XGUnitNativeBase</code></td>
<td>53</td>
<td>Native unit base</td>
</tr>
</tbody>
</table><hr>
<h2 id="architectural-patterns">14. Architectural Patterns</h2>
<h3 id="immutable-state-pattern-gamestate">14.1 Immutable State Pattern (GameState)</h3>
<pre><code>Each XComGameState is immutable once submitted to History.
Modifications create NEW states (delta-based).
Enables: replay, undo, networking sync, serialization.
</code></pre>
<h3 id="context-pattern-who-generates-changes">14.2 Context Pattern (who generates changes)</h3>
<pre><code>XComGameStateContext → XComGameState
  Each state change has a Context that explains:
  - Who caused it (ability, kismet, game rule)
  - What visualization to produce
  - If it was interrupted and by whom
</code></pre>
<h3 id="template-instance-pattern-data-driven">14.3 Template-Instance Pattern (data-driven)</h3>
<pre><code>X2DataTemplate (static, immutable definition)
  → XComGameState_* (runtime instance with mutable state)

Example: X2AbilityTemplate → XComGameState_Ability
         X2CharacterTemplate → XComGameState_Unit
         X2WeaponTemplate → XComGameState_Item
</code></pre>
<h3 id="visualization-action-chain-pattern">14.4 Visualization Action Chain Pattern</h3>
<pre><code>GameState change → Context.BuildVisualization() → X2Action chain
  X2Action_ExitCover → X2Action_Fire → X2Action_ApplyDamage → X2Action_EnterCover
  XComGameStateVisualizationMgr executes the chain sequentially
</code></pre>
<h3 id="manager-singleton-pattern">14.5 Manager Singleton Pattern</h3>
<pre><code>class'XComGameStateHistory'.static.GetGameStateHistory()    → History
class'X2EventManager'.static.GetEventManager()              → Events
class'XComWorldData'.static.GetWorldData()                  → World
class'X2AIJobManager'.static.GetAIJobManager()              → AI Jobs
class'X2AIBTBehaviorTree'.static.GetBehaviorTreeManager()   → Behavior Trees
</code></pre>
<h3 id="delegate-driven-template-pattern">14.6 Delegate-Driven Template Pattern</h3>
<pre><code>Templates use delegates for configurable behavior:
  X2AbilityTemplate: 13 delegates
  X2MissionSourceTemplate: 15 delegates
  X2RewardTemplate: 14 delegates
  X2StaffSlotTemplate: 13 delegates
  X2FacilityTemplate: 11 delegates
</code></pre>
<h3 id="screen-injection-via-uiscreenlistener">14.7 Screen Injection via UIScreenListener</h3>
<pre><code>61+ UIScreenListeners hook existing screens without inheriting:
  event OnInit(UIScreen Screen)          // On open
  event OnReceiveFocus(UIScreen Screen)  // On focus received
  event OnRemoved(UIScreen Screen)       // On close
</code></pre>
<h3 id="condition-chain-pattern-abilities">14.8 Condition Chain Pattern (Abilities)</h3>
<pre><code>Ability available ⟺ ALL conditions are true:
  AbilityShooterConditions[].MeetsCondition()
  AbilityTargetConditions[].MeetsCondition()
  AbilityCosts[].CanAfford()
</code></pre>
<h3 id="state-machine-pattern-ue3-states">14.9 State Machine Pattern (UE3 states)</h3>
<pre><code>Classes with most states:
  X2TacticalGameRuleset: 73 states (tactical game phases)
  XComIdleAnimationStateMachine: 58 states
  XComGameState: 49 states
  PlayerController: 39 states
  XGAIBehavior: 32 states
</code></pre>
<hr>
<h2 id="navigation-guide-by-system">15. Navigation Guide by System</h2>
<h3 id="what-system-do-i-want-to-understand">What system do I want to understand?</h3>

<table>
<thead>
<tr>
<th>System</th>
<th>Key Classes</th>
<th>Package</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>A complete ability</strong></td>
<td><code>X2AbilityTemplate</code>, <code>XComGameStateContext_Ability</code>, <code>X2Effect_*</code>, <code>X2Condition_*</code>, <code>X2Action_*</code></td>
<td>XComGame</td>
</tr>
<tr>
<td><strong>Shooting and damage</strong></td>
<td><code>X2Effect_ApplyWeaponDamage</code>, <code>X2Action_Fire</code>, <code>X2Action_ApplyWeaponDamageToUnit</code>, <code>X2AbilityToHitCalc_StandardAim</code></td>
<td>XComGame</td>
</tr>
<tr>
<td><strong>Overwatch</strong></td>
<td><code>X2Ability_DefaultAbilitySet.OverwatchShot</code>, <code>X2Effect_ReserveOverwatchPoints</code>, <code>X2AbilityTrigger_OnAbilityActivated</code></td>
<td>XComGame</td>
</tr>
<tr>
<td><strong>Tactical movement</strong></td>
<td><code>X2Action_Move*</code>, <code>XComWorldData</code> (pathfinding), <code>X2TacticalGameRuleset</code></td>
<td>XComGame</td>
</tr>
<tr>
<td><strong>Cover system</strong></td>
<td><code>XComCoverInterface</code>, <code>XComWorldData</code> (cover points), macros <code>HAS_COVER_IN_DIR</code></td>
<td>XComGame, Globals.uci</td>
</tr>
<tr>
<td><strong>Turns and phases</strong></td>
<td><code>X2TacticalGameRuleset</code> (73 states), <code>X2GameRuleset</code></td>
<td>XComGame</td>
</tr>
<tr>
<td><strong>Enemy AI</strong></td>
<td><code>XGAIBehavior</code>, <code>X2AIBTBehaviorTree</code>, <code>X2AIBTDefault*</code>, <code>XGAIPlayer</code></td>
<td>XComGame</td>
</tr>
<tr>
<td><strong>Chosen (WOTC)</strong></td>
<td><code>XComGameState_AdventChosen</code>, <code>X2Ability_Chosen*</code>, <code>X2Character_DefaultCharacters</code></td>
<td>XComGame</td>
</tr>
<tr>
<td><strong>Strategic map</strong></td>
<td><code>XComGameState_WorldRegion</code>, <code>XComGameState_MissionSite</code>, <code>UIStrategyMap*</code></td>
<td>XComGame</td>
</tr>
<tr>
<td><strong>Avenger HQ</strong></td>
<td><code>XComGameState_HeadquartersXCom</code>, <code>XComGameState_FacilityXCom</code>, <code>UIFacility_*</code></td>
<td>XComGame</td>
</tr>
<tr>
<td><strong>Research</strong></td>
<td><code>XComGameState_Tech</code>, <code>XComGameState_HeadquartersProjectResearch</code>, <code>X2StrategyElement_DefaultTechs</code></td>
<td>XComGame</td>
</tr>
<tr>
<td><strong>Soldiers</strong></td>
<td><code>XComGameState_Unit</code>, <code>XComCharacterCustomization</code>, <code>XGCharacterGenerator</code></td>
<td>XComGame</td>
</tr>
<tr>
<td><strong>Items/Weapons</strong></td>
<td><code>XComGameState_Item</code>, <code>X2ItemTemplate</code>, <code>X2Item_DefaultWeapons</code>, <code>X2WeaponTemplate</code></td>
<td>XComGame</td>
</tr>
<tr>
<td><strong>Missions</strong></td>
<td><code>XComGameState_MissionSite</code>, <code>X2StrategyElement_DefaultMissionSources</code>, <code>UIMission*</code></td>
<td>XComGame</td>
</tr>
<tr>
<td><strong>Covert actions</strong></td>
<td><code>XComGameState_CovertAction</code>, <code>X2StrategyElement_XpackCovertActions</code></td>
<td>XComGame</td>
</tr>
<tr>
<td><strong>Dark Events</strong></td>
<td><code>XComGameState_DarkEvent</code>, <code>X2StrategyElement_DefaultDarkEvents</code>, <code>X2Ability_DarkEvents</code></td>
<td>XComGame</td>
</tr>
<tr>
<td><strong>WOTC Factions</strong></td>
<td><code>XComGameState_ResistanceFaction</code>, <code>X2StrategyElement_XpackResistanceActions</code></td>
<td>XComGame</td>
</tr>
<tr>
<td><strong>Challenge mode</strong></td>
<td><code>XComChallengeModeManager</code>, <code>UIChallengeMode_*</code>, <code>X2ChallengeModeDataStructures</code></td>
<td>XComGame</td>
</tr>
<tr>
<td><strong>Multiplayer</strong></td>
<td><code>X2MPShellManager</code>, <code>UIMPShell_*</code>, <code>XComMPData</code></td>
<td>XComGame</td>
</tr>
<tr>
<td><strong>Photobooth</strong></td>
<td><code>X2Photobooth</code>, <code>UIPhotoboothBase</code>, <code>X2PhotoBooth_PhotoManager</code></td>
<td>XComGame</td>
</tr>
<tr>
<td><strong>Narrative</strong></td>
<td><code>XComGameState_NarrativeManager</code>, <code>X2DynamicNarrative_*</code>, <code>X2MissionNarrative_*</code></td>
<td>XComGame</td>
</tr>
<tr>
<td><strong>SitReps</strong></td>
<td><code>X2SitRepTemplate</code>, <code>X2SitRep_DefaultSitReps</code>, <code>X2SitRep_DefaultSitRepEffects</code></td>
<td>XComGame</td>
</tr>
<tr>
<td><strong>Alien Rulers [DLC2]</strong></td>
<td><code>XComGameState_AlienRulerManager</code>, <code>X2Ability_DLC_Day60*</code>, <code>X2Helpers_DLC_Day60</code></td>
<td>DLC_2</td>
</tr>
<tr>
<td><strong>SPARK [DLC3]</strong></td>
<td><code>X2Ability_SparkAbilitySet</code>, <code>XComGameState_SparkManager</code>, <code>X2Character_DLC_Day90Characters</code></td>
<td>DLC_3</td>
</tr>
<tr>
<td><strong>Pawns/Visualization</strong></td>
<td><code>XComUnitPawn</code>, <code>XComHumanPawn</code>, <code>XComAlienPawn</code>, <code>XComIdleAnimationStateMachine</code></td>
<td>XComGame</td>
</tr>
<tr>
<td><strong>Sound</strong></td>
<td><code>XComTacticalSoundManager</code>, <code>XComStrategySoundManager</code>, <code>`SOUNDMGR</code></td>
<td>XComGame</td>
</tr>
<tr>
<td><strong>Cheats</strong></td>
<td><code>XComTacticalCheatManager</code> (451f!), <code>XComCheatManager</code>, <code>XComHeadquartersCheatManager</code></td>
<td>XComGame</td>
</tr>
<tr>
<td><strong>Game options</strong></td>
<td><code>UIOptionsPCScreen</code>, <code>XComOnlineProfileSettings</code></td>
<td>XComGame</td>
</tr>
</tbody>
</table><hr>
<h2 id="complexity-analysis-and-optimization">16. Complexity Analysis and Optimization</h2>
<h3 id="most-complex-classes-refactoring-candidates">16.1 Most Complex Classes (refactoring candidates)</h3>

<table>
<thead>
<tr>
<th>Class</th>
<th>Funcs</th>
<th>Lines</th>
<th>Problem</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>XComGameState_Unit</code></td>
<td>546</td>
<td>15,947</td>
<td><strong>God Object</strong> — state, combat, stats, inventory, visibility, everything</td>
</tr>
<tr>
<td><code>XGAIBehavior</code></td>
<td>364</td>
<td>10,870</td>
<td>Concentrates all unit AI logic</td>
</tr>
<tr>
<td><code>XComGameState_HeadquartersXCom</code></td>
<td>331</td>
<td>9,576</td>
<td>Concentrates all HQ logic</td>
</tr>
<tr>
<td><code>PlayerController</code></td>
<td>366</td>
<td>8,841</td>
<td>Deep engine inheritance</td>
</tr>
<tr>
<td><code>XComTacticalCheatManager</code></td>
<td>451</td>
<td>6,750</td>
<td>451 cheat functions</td>
</tr>
<tr>
<td><code>X2Character_DefaultCharacters</code></td>
<td>119</td>
<td>6,312</td>
<td>All character definitions in one class</td>
</tr>
<tr>
<td><code>XComHQPresentationLayer</code></td>
<td>341</td>
<td>6,014</td>
<td>All HQ presentation</td>
</tr>
<tr>
<td><code>X2TacticalGameRuleset</code></td>
<td>150</td>
<td>5,891</td>
<td>73 states — massive state machine</td>
</tr>
<tr>
<td><code>UIAlert</code></td>
<td>167</td>
<td>5,801</td>
<td>All alert types in one class</td>
</tr>
<tr>
<td><code>X2StrategyElement_DefaultObjectives</code></td>
<td>199</td>
<td>4,513</td>
<td>All objectives in one function</td>
</tr>
</tbody>
</table><h3 id="coupling-—-most-referenced-classes">16.2 Coupling — Most Referenced Classes</h3>

<table>
<thead>
<tr>
<th>Class</th>
<th>References</th>
<th>Type</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>UIUtilities_Input</code></td>
<td>284</td>
<td>Utility (OK — helpers only)</td>
</tr>
<tr>
<td><code>XComGameState_HeadquartersXCom</code></td>
<td>242</td>
<td><strong>God Object</strong> — many classes depend on HQ</td>
</tr>
<tr>
<td><code>XComGameStateContext_ChangeContainer</code></td>
<td>229</td>
<td>Change pattern (OK — correct usage)</td>
</tr>
<tr>
<td><code>UIUtilities_Text</code></td>
<td>220</td>
<td>Utility (OK)</td>
</tr>
<tr>
<td><code>XComGameState_Unit</code></td>
<td>216</td>
<td><strong>God Object</strong> — used by almost everything</td>
</tr>
<tr>
<td><code>X2StrategyGameRulesetDataStructures</code></td>
<td>148</td>
<td>Data structures (OK — definitions)</td>
</tr>
<tr>
<td><code>WorldInfo</code></td>
<td>138</td>
<td>Engine singleton (OK)</td>
</tr>
<tr>
<td><code>X2AbilityTemplateManager</code></td>
<td>131</td>
<td>Template manager (OK)</td>
</tr>
<tr>
<td><code>XComGameState_BattleData</code></td>
<td>118</td>
<td>Battle data (moderate coupling)</td>
</tr>
<tr>
<td><code>XComWorldData</code></td>
<td>111</td>
<td>World data (OK — world data)</td>
</tr>
</tbody>
</table><h3 id="native-functions-as-hot-path-indicators">16.3 Native Functions as Hot Path Indicators</h3>
<p>Classes with the most native functions (C++) indicate the most performance-critical areas:</p>

<table>
<thead>
<tr>
<th>Class</th>
<th>Native</th>
<th>Area</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>XComWorldData</code></td>
<td>161</td>
<td><strong>Pathfinding, LOS, tiles</strong> — bottleneck #1</td>
</tr>
<tr>
<td><code>Actor</code></td>
<td>123</td>
<td>Engine base — transforms, collisions</td>
</tr>
<tr>
<td><code>XComGameState_Unit</code></td>
<td>114</td>
<td>Stats, visibility, combat checks</td>
</tr>
<tr>
<td><code>SkeletalMeshComponent</code></td>
<td>114</td>
<td>Animation — rendering</td>
</tr>
<tr>
<td><code>OnlineSubsystemSteamworks</code></td>
<td>113</td>
<td>Networking — Steam</td>
</tr>
<tr>
<td><code>Object</code></td>
<td>94</td>
<td>Reflection, serialization, garbage collection</td>
</tr>
<tr>
<td><code>XComEngine</code></td>
<td>70</td>
<td>Main engine loop</td>
</tr>
</tbody>
</table><h3 id="shared-state-—-potential-race-conditions">16.4 Shared State — Potential Race Conditions</h3>
<ul>
<li><code>XComGameStateHistory</code> is a mutable singleton accessed by gameplay, UI, AI, and networking</li>
<li>The Visualization system is tightly coupled to the gameplay loop</li>
<li><code>ELD_Immediate</code> event listeners modify state during evaluation</li>
</ul>
<h3 id="optimization-opportunities">16.5 Optimization Opportunities</h3>
<ol>
<li>
<p><strong>XComGameState_Unit</strong> (15,947l) → Decompose into components:</p>
<ul>
<li>UnitCombatComponent (stats, damage, effects)</li>
<li>UnitInventoryComponent (items, loadout)</li>
<li>UnitVisibilityComponent (LOS, cover, detection)</li>
<li>UnitProgressionComponent (XP, abilities, traits)</li>
</ul>
</li>
<li>
<p><strong>XGAIBehavior</strong> (10,870l) → Move conditions and actions to separate classes by type (already partially done with BT but the base class remains massive)</p>
</li>
<li>
<p><strong>X2Character_DefaultCharacters</strong> (6,312l) → Each character could be a separate class or read from data files</p>
</li>
<li>
<p><strong>History.GetGameStateForObjectID()</strong> — 1,214 uses. Cache results where possible to avoid repeated lookups</p>
</li>
<li>
<p><strong>UIScreenListener pattern</strong> — 61+ listeners could be consolidated per screen</p>
</li>
</ol>
<hr>
<h2 id="global-statistics">17. Global Statistics</h2>
<h3 id="base-game-totals">17.1 Base Game Totals</h3>

<table>
<thead>
<tr>
<th>Metric</th>
<th>Value</th>
</tr>
</thead>
<tbody>
<tr>
<td>Base packages</td>
<td>15</td>
</tr>
<tr>
<td>Total classes</td>
<td>4,164</td>
</tr>
<tr>
<td>Total functions</td>
<td>~33,559</td>
</tr>
<tr>
<td>Lines of code</td>
<td>~915,714</td>
</tr>
<tr>
<td>Native functions (C++)</td>
<td>4,092</td>
</tr>
<tr>
<td>.uci files (macros)</td>
<td>16</td>
</tr>
<tr>
<td>Maximum inheritance depth</td>
<td>9 levels</td>
</tr>
<tr>
<td>Defined structs</td>
<td>~500+</td>
</tr>
<tr>
<td>Defined enums</td>
<td>~300+</td>
</tr>
<tr>
<td>Config files used</td>
<td>15 types</td>
</tr>
</tbody>
</table><h3 id="xcomgame-the-main-package">17.2 XComGame (the main package)</h3>

<table>
<thead>
<tr>
<th>Category</th>
<th>Classes</th>
<th>Lines</th>
<th>Top Class</th>
</tr>
</thead>
<tbody>
<tr>
<td>UI</td>
<td>533</td>
<td>190,393</td>
<td>UIAlert (5,801l)</td>
</tr>
<tr>
<td>XCom* classes</td>
<td>363</td>
<td>107,984</td>
<td>XComTacticalCheatManager (6,750l)</td>
</tr>
<tr>
<td>GameState</td>
<td>106</td>
<td>85,133</td>
<td>XComGameState_Unit (15,947l)</td>
</tr>
<tr>
<td>Abilities</td>
<td>134</td>
<td>51,973</td>
<td>X2Ability_Chosen (2,930l)</td>
</tr>
<tr>
<td>Strategy Elements</td>
<td>46</td>
<td>36,926</td>
<td>X2StrategyElement_DefaultObjectives (4,513l)</td>
</tr>
<tr>
<td>XG* (legacy)</td>
<td>69</td>
<td>40,196</td>
<td>XGAIBehavior (10,870l)</td>
</tr>
<tr>
<td>X2Actions</td>
<td>199</td>
<td>23,619</td>
<td>X2Action_ApplyWeaponDamageToUnit (1,313l)</td>
</tr>
<tr>
<td>Items</td>
<td>20</td>
<td>17,549</td>
<td>X2Item_DefaultWeapons (4,574l)</td>
</tr>
<tr>
<td>Effects</td>
<td>204</td>
<td>16,306</td>
<td>X2Effect_ApplyWeaponDamage (1,709l)</td>
</tr>
<tr>
<td>Seq/Kismet</td>
<td>279</td>
<td>16,044</td>
<td>SeqEvent_HQUnits (391l)</td>
</tr>
<tr>
<td>Challenge Mode</td>
<td>43</td>
<td>15,172</td>
<td>UIChallengeMode_SquadSelect (2,529l)</td>
</tr>
<tr>
<td>Photobooth</td>
<td>19</td>
<td>10,050</td>
<td>X2Photobooth (3,523l)</td>
</tr>
<tr>
<td>Templates</td>
<td>87</td>
<td>8,043</td>
<td>X2AbilityTemplate (1,044l)</td>
</tr>
<tr>
<td>AI</td>
<td>10</td>
<td>6,639</td>
<td>X2AIBTDefaultConditions (2,737l)</td>
</tr>
<tr>
<td>Characters</td>
<td>2</td>
<td>7,730</td>
<td>X2Character_DefaultCharacters (6,312l)</td>
</tr>
<tr>
<td>Conditions</td>
<td>49</td>
<td>2,106</td>
<td>X2Condition_UnitInteractions (107l)</td>
</tr>
<tr>
<td>SitReps</td>
<td>26</td>
<td>1,668</td>
<td>X2SitRep_DefaultSitRepEffects (727l)</td>
</tr>
</tbody>
</table><h3 id="top-15-most-used-interfaces">17.3 Top 15 Most Used Interfaces</h3>

<table>
<thead>
<tr>
<th>Interface</th>
<th>Implementors</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>X2VisualizedInterface</code></td>
<td>~20+ (Unit, Cheats, Destructible, EvacZone, etc.)</td>
</tr>
<tr>
<td><code>X2GameRulesetVisibilityInterface</code></td>
<td>~10+ (Unit, Destructible, SquadViewer)</td>
</tr>
<tr>
<td><code>Lootable</code></td>
<td>Unit, InteractiveObject, LootDrop</td>
</tr>
<tr>
<td><code>Damageable</code></td>
<td>Unit, Destructible</td>
</tr>
<tr>
<td><code>Hackable</code></td>
<td>Unit, InteractiveObject</td>
</tr>
<tr>
<td><code>UIQueryInterfaceUnit</code></td>
<td>Unit</td>
</tr>
<tr>
<td><code>UIQueryInterfaceItem</code></td>
<td>Item</td>
</tr>
<tr>
<td><code>UIQueryInterfaceAbility</code></td>
<td>Ability</td>
</tr>
<tr>
<td><code>IUISortableScreen</code></td>
<td>Various UI screens</td>
</tr>
</tbody>
</table><hr>
<h2 id="practical-optimization-guide">18. Practical Optimization Guide</h2>
<h3 id="golden-rules-of-optimization">18.1 Golden Rules of Optimization</h3>
<h4 id="minimize-history-accesses">Minimize <code>History</code> accesses</h4>
<ul>
<li><code>History.GetGameStateForObjectID()</code> is one of the most expensive calls.</li>
<li>Avoid using it inside loops.</li>
<li>Always cache results when possible.</li>
</ul>
<hr>
<h4 id="group-changes-in-a-single-gamestate">Group changes in a single <code>GameState</code></h4>
<ul>
<li>Each <code>SubmitGameState</code> generates synchronization and snapshots.</li>
<li>Reduce the number of submits to a minimum.</li>
</ul>
<hr>
<h4 id="order-evaluations-from-cheap-to-expensive">Order evaluations from cheap to expensive</h4>
<ul>
<li>Especially in abilities.</li>
<li>Use aggressive early returns.</li>
</ul>
<hr>
<h4 id="avoid-redundant-work-in-the-ability-pipeline">Avoid redundant work in the Ability Pipeline</h4>
<ul>
<li>Conditions, Costs, and Effects are evaluated many times per turn.</li>
<li>Do not duplicate logic.</li>
</ul>
<hr>
<h4 id="avoid-eld_immediate-unless-critically-necessary">Avoid <code>ELD_Immediate</code> unless critically necessary</h4>
<ul>
<li>Can cause event cascades and hard-to-debug bugs.</li>
<li>Prefer deferred events.</li>
</ul>
<hr>
<h4 id="cache-xcomgamestate_unit">Cache <code>XComGameState_Unit</code></h4>
<ul>
<li>It is the most accessed object in the game.</li>
<li>Avoid multiple lookups.</li>
</ul>
<hr>
<h4 id="keep-the-ui-lightweight">Keep the UI lightweight</h4>
<ul>
<li><code>UIScreenListener</code> can impact global performance.</li>
<li>Do not perform heavy logic there.</li>
</ul>
<hr>
<h4 id="reduce-unnecessary-loops">Reduce unnecessary loops</h4>
<ul>
<li>Avoid O(n²)</li>
<li>Filter before iterating</li>
</ul>
<hr>
<h4 id="prefer-data-driven-design-templates">Prefer data-driven design (Templates)</h4>
<ul>
<li>Avoid unnecessary runtime calculations</li>
</ul>
<hr>
<h4 id="do-not-optimize-native-code">Do not optimize native code</h4>
<ul>
<li><code>XComWorldData</code>, pathfinding, LOS → already optimized in C++</li>
</ul>
<hr>
<h3 id="quick-debug-checklist">18.2 Quick Debug Checklist</h3>
<h4 id="gamestate">GameState</h4>
<ul>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> Is there <code>History.GetGameStateForObjectID</code> inside loops?</li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> Am I caching correctly?</li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> Am I using multiple <code>SubmitGameState</code> calls?</li>
</ul>
<hr>
<h4 id="ability-system">Ability System</h4>
<ul>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> Did I order conditions from cheap to expensive?</li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> Did I avoid duplicated logic?</li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> Are there heavy calculations in ToHit?</li>
</ul>
<hr>
<h4 id="loops">Loops</h4>
<ul>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> Are there unnecessary nested loops?</li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> Am I iterating more than necessary?</li>
</ul>
<hr>
<h4 id="events">Events</h4>
<ul>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> Am I using <code>ELD_Immediate</code>?</li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> Can it cause cascades?</li>
</ul>
<hr>
<h4 id="ui">UI</h4>
<ul>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> Does this listener always run?</li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> Am I using History inside the UI?</li>
</ul>
<hr>
<h4 id="general">General</h4>
<ul>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> Does this run many times per turn?</li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> Is it part of AI / abilities?</li>
</ul>
<hr>
<h3 id="common-anti-patterns">18.3 Common Anti-Patterns</h3>
<h4 id="history-spam-in-loops">History spam in loops</h4>
<pre class=" language-unrealscript"><code class="prism  language-unrealscript">foreach Units
{
    Unit = XComGameState_Unit(History.GetGameStateForObjectID(ID));
}
</code></pre>
<hr>
<h4 id="gamestate-fragmentation">GameState fragmentation</h4>
<pre class=" language-unrealscript"><code class="prism  language-unrealscript">SubmitGameState(A);
SubmitGameState(B);
</code></pre>
<hr>
<h4 id="duplicated-logic-in-abilities">Duplicated logic in abilities</h4>
<ul>
<li>Conditions</li>
<li>Costs</li>
<li>Effects</li>
</ul>
<hr>
<h4 id="abuse-of-eld_immediate">Abuse of <code>ELD_Immediate</code></h4>
<ul>
<li>Cascades</li>
<li>Hard-to-debug bugs</li>
</ul>
<hr>
<h4 id="ui-with-gameplay-logic">UI with gameplay logic</h4>
<ul>
<li>Silent but constant performance impact</li>
</ul>
<hr>
<h4 id="on²-loops">O(n²) loops</h4>
<pre class=" language-unrealscript"><code class="prism  language-unrealscript">foreach Units
{
    foreach Units
    {
    }
}
</code></pre>
<hr>
<h4 id="recalculating-everything-constantly">Recalculating everything constantly</h4>
<ul>
<li>Especially in AI</li>
</ul>
<hr>
<h4 id="repeated-casts">Repeated casts</h4>
<ul>
<li>Inside loops</li>
</ul>
<hr>
<h3 id="applied-examples">18.4 Applied Examples</h3>
<h4 id="unit-caching">Unit caching</h4>
<pre class=" language-unrealscript"><code class="prism  language-unrealscript">// Before
foreach TargetIDs
{
    TargetUnit = XComGameState_Unit(History.GetGameStateForObjectID(TargetID));
}

// After
TargetUnit = CachedUnits[TargetID];
</code></pre>
<hr>
<h4 id="early-return-in-abilities">Early return in abilities</h4>
<pre class=" language-unrealscript"><code class="prism  language-unrealscript">if (!HasAP()) return false;
if (!ExpensiveCheck()) return false;
</code></pre>
<hr>
<h4 id="consolidated-gamestate">Consolidated GameState</h4>
<pre class=" language-unrealscript"><code class="prism  language-unrealscript">NewGameState = CreateGameState();

ApplyEffectA(NewGameState);
ApplyEffectB(NewGameState);

SubmitGameState(NewGameState);
</code></pre>
<hr>
<h4 id="avoid-logic-in-ui">Avoid logic in UI</h4>
<pre class=" language-unrealscript"><code class="prism  language-unrealscript">// Better: use precomputed data
CachedData = GetPrecomputedData();
</code></pre>
<hr>
<h3 id="master-rule">18.5 Master Rule</h3>
<blockquote>
<p><strong>If it runs many times per turn → optimize it first</strong></p>
<p>(Abilities, AI, events, loops)</p>
</blockquote>
<hr>
<blockquote>
<p><strong>How to use this knowledge base:</strong> Use the <a href="#15-navigation-guide">Navigation Guide (Section 15)</a> to quickly locate relevant code for any system. Consult the <a href="#9-global-macro-system">Global Macros (Section 9)</a> before reading any code to understand the shortcuts. For optimization, review <a href="#16-complexity-analysis">Section 16</a> and <a href="#18-optimization-guide">Section 18</a>.</p>
</blockquote>

