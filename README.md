# MVVM Wizard
 
MvvmWizard gives possibility to create wizard with steps in simply manner.
It's highly configurable with set of built-in options and styles.
<br />
Supports [MahApps.Metro](https://mahapps.com/) themes

## Demo
* [bin](https://github.com/worker-it/mvvm-wizard/releases/download/1.1.1/mvvm-wizrard-demo-bin.zip)
* [code](https://github.com/worker-it/mvvm-wizard/tree/master/src/WizardDemo)

<div>
<img alt="simpledemo" src="./docs/demo_wizard.gif">
</div>

## Usage
[Documentation](https://github.com/lezhkin11/mvvm-wizard/wiki)

### 1 Set ViewResolver
CSharp
```csharp
using MvvmWizard.Classes;
using Unity;

var unityContainer = new UnityContainer();
WizardSettings.Instance.ViewResolver = viewType => unityContainer.Resolve(viewType);
```
VB
```vb
Imports MvvmWizard.Classes
Imports Unity

WizardSettings.Instance.ViewResolver = Function(ByVal arg As Type) As Object
                                           Return New UnityContainer().Resolve(arg)
                                       End Function
```

### 2 Create Wizard Control
`xmlns:controls="clr-namespace:MvvmWizard.Controls;assembly=MvvmWizard"
xmlns:simple="clr-namespace:Your.Namespace.For.Views"`

```xml
<controls:Wizard FinishCommand="{Binding CloseCommand}">
    <controls:WizardStep ViewType="{x:Type simple:WelcomeView}" BackButtonVisibility="Collapsed" />
    <controls:WizardStep ViewType="{x:Type simple:RegistrationView}" />
    <controls:WizardStep ViewType="{x:Type simple:RegistrationSummaryView}" ForwardButtonTitle="Finish" />
</controls:Wizard>
```
### Licence
[MIT License (MIT)](./LICENSE)
