---
title: インプレース アップグレードによる Windows 10 Enterprise の既存デバイスへの展開
description: 構成して、インプレース アップグレードとシステム センター構成マネージャーを使用して、10 企業の Windows イメージを展開するのには、ガイダンスを提供します。
keywords: Microsoft 365、Microsoft 365 エンタープライズでは、Microsoft 365 ドキュメント、Windows 10 の企業展開では、インプレース アップグレード、構成マネージャーでは、システム センター構成マネージャー
author: greg-lindsay
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2018
ms.author: greglin
ms.openlocfilehash: 3df76c0de7b5a8b12c063113c79f9efa4e33b4c1
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869521"
---
# <a name="step-2-deploy-windows-10-enterprise-for-existing-devices-as-an-in-place-upgrade"></a>手順 2: インプレース アップグレードによる Windows 10 Enterprise の既存のデバイスへの展開

*この記事は、Microsoft 365 Enterprise の E3 および E5 の両バージョンに適用されます*

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Windows 10 Windows 7 または Windows 8.1 を現在実行中の Pc をアップグレードする最も簡単なパスでは、インプレース アップグレードをします。システム センター構成マネージャー (構成マネージャー) のタスク シーケンスを使用すると、プロセスを完全に自動化します。 

Windows 7 または Windows 8.1 を実行している既存のコンピューターがある場合は、組織が 10 の Windows を展開する場合はこのパスが勧めします。これには、Windows のインストール プログラム (Setup.exe) すべてのデータ、設定、アプリケーションを自動的に保持する、インプレース アップグレードを実行して、既存のオペレーティング システムのバージョンのドライバーが利用しています。どのような複雑な展開インフラストラクチャの必要性がないために、最小限の IT 作業が必要です。

これらの手順を構成し、構成マネージャーを使用して、インプレース アップグレードとして 10 企業の Windows イメージを展開します。

## <a name="part-1-verify-readiness-to-upgrade-windows"></a>パート 1: Windows をアップグレードする準備を確認

強力な洞察と、コンピューター、アプリケーション、およびドライバーを必要とせず、組織内の推奨事項を提供する Windows の分析機能のアップグレードの準備機能を使用して最初に、余分なコストと、追加のインフラストラクチャ要件なし。この新しいサービスでは、マイクロソフトの推奨事項に基づいてワークフローを使用して更新プロジェクトをアップグレードし、機能を説明します。最新のインベントリ データは、コストのバランスと、アップグレード プロジェクトのリスクにできます。

詳細については、開始、使用、および準備のアップグレードのトラブルシューティングを行うには、[アップグレードの準備を管理する Windows のアップグレード](https://docs.microsoft.com/windows/deployment/upgrade/manage-windows-upgrades-with-upgrade-readiness)を参照してください。

次に、以下の Windows 7 またはそれ以降のオペレーティング システムを Windows の 10 にアップグレードするのにはシステム センター構成マネージャー (現在の分岐) を使用するガイドです。同様に危険度の高い展開を続行する前にユーザー データのバックアップをお勧めします。OneDrive クラウド ストレージはライセンスを受けたマイクロソフト 365 ユーザーに使用する準備ができてし、安全にファイルを格納する使用することができます。詳細については、 [OneDrive のクイック スタート ガイド](https://aka.ms/ODfBquickstartguide)を参照してください。このページにアクセスするに、テナント管理や、Office 365 または Microsoft 365 テナント内のグローバル管理者としてサインインする必要があります。

構成マネージャーのバージョンとサポートされている Windows の 10 クライアントの対応するバージョンのリストは、[サポートの Windows 10 ですシステム センター構成マネージャーを](https://aka.ms/supportforwin10sccm)参照してください。

**Windows をアップグレードする準備を確認するのには**

10 の Windows の展開を開始する前にこれらの要件を確認してください。

- **対象となる Windows のエディションのアップグレード**で、デバイスは、10 企業の Windows へのアップグレードの対象となるエディションの Windows 7 または Windows 8.1 を実行している必要があります。サポートされているエディションの一覧は、[アップグレード パスの Windows 10](https://aka.ms/win10upgradepaths)を参照してください。 
- **サポートされているデバイス**の Windows 8.1 に対応しているほとんどのコンピューターは 10 の Windows と互換性のあるになります。10 の Windows で正しく機能するデバイスの更新されたドライバーをインストールする必要があります。詳細については、 [Windows の 10 の仕様](https://aka.ms/windows10specifications)を参照してください。
- **導入準備**・展開の構成を開始する前に次があるかどうかを確認します。
    - 10 の Windows インストール メディアからインストール メディアは、すでにマウントされている iso 別のドライブに置く必要があります。[MSDN サブスクライバー ダウンロード](https://aka.ms/msdn-subscriber-downloads)から、または[ボリューム ライセンス サービス センター](https://aka.ms/mvlsc)からは、ISO を取得できます。
    - ユーザー データのバックアップ、アップグレードでは、ユーザー データは移行のベスト プラクティスはバックアップのシナリオを構成するのにはたとえば、OneDrive アカウント、BitLocker To Go で暗号化された USB フラッシュ ドライブ、またはネットワーク ファイル サーバーにすべてのユーザー データをエクスポートします。詳細については、[バックアップまたは Windows でのデータ転送](https://aka.ms/backuptransferdatawindows)を参照してください。
- **環境の準備**- 既存の構成マネージャー サーバーの構造を使用して、オペレーティング システムの展開を準備します。ベースのセットアップでは、他構成マネージャーの環境で以下の構成を変更する必要があります。
    1. [Active Directory スキーマを拡張して](https://aka.ms/extendadschema) [、System Management コンテナーを作成](https://aka.ms/createsysmancontainer)します。
    2. 探索を有効にする Active Directory フォレストおよび Active Directory システム探索します。詳細については、[探索方法の構成のシステム センター構成マネージャー](https://aka.ms/configurediscoverymethods)を参照してください。
    3. IP の範囲の境界と境界のグループのコンテンツおよびサイトの割り当てを作成します。詳細については、[サイト境界を定義し境界グループのシステム センター構成マネージャー](https://aka.ms/definesiteboundaries)を参照してください。
    4. 追加し、レポート サービス ポイントの役割の構成マネージャーを構成します。詳細については、[構成マネージャーでのレポート作成を構成する](https://aka.ms/configurereporting)を参照してください。
    5. パッケージをファイル システムのフォルダー構造を作成します。
    6. パッケージの構成マネージャー コンソールのフォルダー構造を作成します。
    7. システム センター構成マネージャー (現在の分岐) の更新プログラムおよびその他の Windows 10 必要条件をインストールします。

## <a name="part-2-add-a-windows-10-os-image-using-configuration-manager"></a>パート 2: 構成マネージャーを使用する 10 の Windows OS イメージを追加します。
今すぐフル 10 の Windows インストール メディアが含まれるオペレーティング システムのアップグレード パッケージを作成する必要があります。次の手順では、10 企業の Windows x64 にアップグレード パッケージを作成するのには構成マネージャーを使用します。

**構成マネージャーを使用する 10 の Windows OS のイメージを追加するのには**

1. **ソフトウェア ライブラリ**のワークスペースで、構成マネージャー コンソールを使用して、**オペレーティング システムのアップグレード パッケージ**] ノードを右クリックし、**オペレーティング システムのアップグレード パッケージの追加**します。
2. [**データ ソース**] ページで、10 企業の Windows x64 メディアへの UNC パスを指定し、**次へ**します。
3. [**全般**] ページでは、 **10 企業の Windows x64 にアップグレード**するにはを指定し、**次へ**を選択します。 
4. [**概要**] ページで、**次へ**を選択し、[**閉じる**] を選択します。 
5. 作成の**10 企業の Windows x64 の更新プログラム**パッケージを右クリックし、**コンテンツを配布**します。 
6. 配布ポイントを選択します。

## <a name="part-3-configure-deployment-settings"></a>パート 3: 展開設定を構成します。
ここでは、Windows の 10 のアップグレードの設定が含まれているアップグレード ・ タスクのシーケンスを構成します。アップグレードして、デバイスを識別し、および、それらのデバイスにタスク シーケンスを展開します。

### <a name="create-a-task-sequence"></a>タスク シーケンスを作成します。
アップグレードのタスク シーケンスを作成するには、次の手順を実行します。
  
1. 構成マネージャー コンソールで、[**ソフトウェア ライブラリ**] ワークスペースでは、**オペレーティング システム**を展開します。 
2. **タスク シーケンス**] ノードを右クリックし、**タスク シーケンスを作成**します。
3. [**新しいタスク シーケンスの作成**] ページでは、**アップグレード パッケージからオペレーティング システムのアップグレード**をするを選択し、**次へ**を選択します。
4. [**タスク シーケンス情報**] ページで、 **10 企業の Windows x64 にアップグレード**するかを指定し、**次へ**します。
5. **Windows オペレーティング システムのアップグレード**] ページで、[**参照...** ] と**オペレーティング システムのアップグレード Windows 10 エンタープライズ x64 パッケージをアップグレード**する」を選択、 **[ok]** を選択し、**次へ**。
6. 残りのウィザード ページを続行し、[**閉じる**] を選択します。

### <a name="create-a-device-collection"></a>デバイスのコレクションを作成します。
アップグレードのタスク シーケンスを作成した後は、アップグレードするデバイスを含むコレクションを作成する必要があります。

> [!NOTE]
> 1 つのデバイスの配置をテストするのにには、次の設定を使用します。準備ができたら、デバイス ・ グループを含めるには、さまざまなメンバーシップの規則を使用できます。詳細については、[システム センター構成マネージャーでのコレクションを作成する方法](https://aka.ms/sccm-create-collections)を参照してください。

1. 構成マネージャー コンソールで、[**資産と法令遵守**のワークスペースで、**デバイスのコレクション**を右クリックし、**デバイスのコレクションを作成**します。 
2. デバイス コレクションの作成ウィザードで、[**全般**] ページで、次の設定を入力して、**次へ**を選択します。
    - 名前: 10 の Windows x64 のエンタープライズのアップグレード
    - すべてのシステムの制限のコレクション。
3. [**メンバーシップの規則**] ページで、**ルールの追加**を選択して > 、ダイレクト メンバーシップ規則作成ウィザードを起動するのには**直接のルール**です。
4. ダイレクト メンバーシップ規則作成ウィザードの [**ようこそ**] ページで**次**のように選択します。
5. **リソースの検索**ページで、アップグレードするデバイスの名前と**値**のテキストのプレース ホルダーを置き換える、次の設定を入力します。 
    - システム リソースのリソース クラス。
    - 属性名: 名前
    - 値: *PC0003*
6. [**リソースの選択**] ページで、デバイスを選択] をクリック**します**。
7. ダイレクト メンバーシップの規則の作成ウィザードとデバイスのコレクションの作成ウィザードを完了します。  
8. 10 エンタープライズの Windows x64 のアップグレードのコレクションを確認します。マシンが表示されるまで続行しないでコレクションに追加します。

### <a name="create-an-operating-system-deployment"></a>オペレーティング システムの展開を作成します。
展開のタスク シーケンスを作成するのにはこれらの手順に従います。

1. 構成マネージャー コンソールで、[**ソフトウェア ライブラリ**] ワークスペースで、前の手順で作成したタスク シーケンスを右クリックし、**展開**します。
2. [**全般**] ページで、コレクションを選択**10 企業の Windows x64 のアップグレード**、**次へ**を選択します。
3. [**コンテンツ**] ページで、**次**の手順を選択します。
4. [**展開の設定**] ページで、次の設定を選択し、し、[**次へ**。

    > [!NOTE]
    > このテスト展開では、**利用可能な**展開を開始するユーザーの介入を必要とする目的を設定します。本番環境で、必要な目的があり、展開の実行時の設定などの他のオプションを構成するを使用して展開を自動化することもできます。 

    - アクション: インストール
    - 目的: 利用可能な

5. [**スケジュール**] ページで、既定の設定をそのまま使用し、し、**次**のように選択します。
6. [**ユーザー エクスペリエンス**] ページで既定の設定をそのまま使用し、**次へ**します。
7. [**アラート**] ページで、既定の設定をそのまま使用し、し、**次**のように選択します。
8. [**概要**] ページで、**次へ**を選択し、[**閉じる**] を選択します。

## <a name="part-5-start-the-windows-10-upgrade-task-sequence"></a>パート 5: アップグレード タスクのシーケンスを開始 Windows 10
アップグレードするデバイス上の Windows 10 へのアップグレードのタスク シーケンスを起動するのにはこれらの手順に従います。
 
1. Windows コンピューターにログオンし、**ソフトウェア センター**を起動します。
2. 前の手順で作成したタスク シーケンスを選択し、**インストール**を選択します。
3. タスク シーケンスが開始されると、自動的に開始、インプレース アップグレード プロセスを呼び出して、Windows のセットアップ プログラム (Setup.exe) すべてのデータ、設定、アプリケーションを維持する、自動アップグレードを実行するために必要なコマンド ライン パラメーターをドライバーです。
4. タスク シーケンスが正常に完了した後は、このコンピューターが完全に Windows の 10 にアップグレードされます。

エンタープライズ環境で Windows 10 を使用するときに問題が発生した場合、「[最も一般的な問題に対する上位の Microsoft サポート ソリューション](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions)」 を参照してください。これらのリソースには、サポート技術情報の記事、更新情報、およびライブラリの記事が含まれます。

組織全体の更新のロールアウトでは、OS の更新の対応、展開の進捗状況の更新、および障害の 10 の Windows のデバイスのトラブルシューティングの全体像を提供するのに Windows の分析のコンプライアンスの更新機能を使用します。この新しいサービスを必要とせず、このような洞察を提供するインストールの進行状況、Windows 更新プログラムの構成、およびその他の情報を含む、診断データを使用して余分なコストと、追加のインフラストラクチャ要件なし。ビジネスやその他の管理ツールの Windows Update を使用するかどうかすることを確認できます、デバイスを適切に更新します。

[モニター Windows の更新プログラムと Windows Defender のウイルス対策の更新の対応の](https://docs.microsoft.com/windows/deployment/update/update-compliance-monitor)詳細については、開始、および更新の対応を使用するを参照してください。

中間チェックポイントとして、この手順に対応する[終了条件](windows10-exit-criteria.md#crit-windows10-step2)を確認できます。

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [Windows Autopilot を使用して新しいデバイスに Windows 10 Enterprise を展開する](windows10-deploy-autopilot.md) |



<!--

| Phases | Description |
|:--- |:--- |
| [Phase 1: Consideration phase](#phase-1-consideration-phase) | TBD |
| [Phase 2: Testing phase](#phase-2-testing-phase) | TBD |
| [Phase 3: Deployment phase](#phase-3-deployment-phase) | TBD |

## Phase 1: Consideration phase
Before upgrading an OS in an enterprise environment, take the following technical aspects into account:
* [Infrastructure](#step-1-infrastructure)
* [Apps](#step-2-apps)
* [Governance and business processes](#step-3-governance-and-business-processes)

This guide is meant only to provide Microsoft's best recommendations around these assumptions by providing links to existing documentation.

### Step 1: Infrastructure
Consider your organization's collection of hardware, software, policies, networks, and other related technologies as part of the deployment process.

For in-place upgrade with Configuration Manager, these are the infrastructure you need to take into account:

#### Group Policy
Windows 10 introduces many new features and removes and changes many others in Windows 7 and 8.1, including new Group Policy settings which you need to test and implement as part of a Windows 10 migration. Use the examples from the following resources to assess current group policies for Windows, including Group Policy Objects in the Active Directory structure:
* [Manage Windows 10 with administrative templates](https://go.microsoft.com/fwlink/?linkid=860226) - Get step-by-step info on how to manage Windows 10 with administrative templates
* [Group Policy settings that apply to Windows 10](https://docs.microsoft.com/windows/client-management/group-policies-for-enterprise-and-education-editions) - Find out which Group Policy settings apply only to Windows 10 Enterprise

> [!NOTE]
> If you are considering moving to modern management by using MDM instead of Group Policy to manage device configurations, you can start by using the [MDM Migration Analysis Tool (MMAT)](https://github.com/WindowsDeviceManagement/MMAT) to determine what Group Policies are set on the device and report the corresponding settings, if available.

#### Data management
Although in-place upgrades shouldn’t affect user data and apps, a best practice is to configure a backup scenario and back up user data. For example, export all user data to a OneDrive for Business account, BitLocker To Go-encrypted USB flash drive, or network file server. For more details, see:
* [How to back up or transfer your data on a Windows-based computer](https://go.microsoft.com/fwlink/?linkid=860230) - Get step-by-step info on how to manually back up your personal files and settings.
* [Redirect known folders to OneDrive for Business](https://go.microsoft.com/fwlink/?linkid=846620) - Learn how to set a policy at the domain level to make sure users all sync to the same folder when they install the OneDrive sync client and how you can set additional policies to redirect the Documents folder to that sync location.

#### System Center Configuration Manager
This guide assumes you are following Microsoft recommendations and have one of the following versions of System Center Configuration Manager 2012 onward:
* System Center 2012 Configuration Manager with SP2
* System Center 2012, 2012 R2 Configuration Manager with SP1, Current Branch, 1706
    * [Run an in-place upgrade to the latest Configuration Manager](https://go.microsoft.com/fwlink/?linkid=839406)
    * [Updates for Configuration Manager](https://go.microsoft.com/fwlink/?linkid=620343)
* Core Configuration Manager configuration:
    * CONFIGURATION MANAGER accounts
    * Active Directory permissions
    * Source folder structure
    * Active Directory schema
* Configure the following [necessary Configuration Manager components for Windows 10 deployment](https://go.microsoft.com/fwlink/?linkid=860245):
    * **State migration point** - Stores user state migration data during computer replace scenarios
    * **Distribution point** - Stores all packages in Configuration Manager
    * **Software update point** - Updates an OS as part of the deployment process
    * **Reporting services point** - Monitors the OS deployment process
    * **Boot images** - Are Windows Preinstallation Environment (PE) images used by Configuration Manager to start deployments
    * **OS images** - Denotes the production deployment image (mounted OS)
    * **OS installers** - Creates reference images using Microsoft Deployment Toolkit (MDT) Light Touch
    * **Drivers** - Denotes a repository of managed device drivers
    * **Task Sequence** - Is delivered automatically to the client as a policy

#### Network bandwidth
This guide assumes you have enough network bandwidth to support the deployment of Windows 10 Enterprise and Office 365 ProPlus as a unit. As a bundle, network bandwidth is a significant factor.

#### Client machines and in-place upgrade scenario
* Disk encryption - Third-party disk encryption isn't supported in an in-place upgrade scenario.
* User profiles - Only the standard user profile type is supported.
* Legacy BIOS to Unified Extensible Firmware Interface (UEFI) booting - Changing from legacy BIOS to UEFI booting isn't supported.
* Dual-boot - This scenario is not covered in the guide. If you have the FastTrack Benefit, it only covers devices running a single OS.
* Virtual desktop infrastructure (VDI) environments - This scenario is not covered in the guide. If you have the FastTrack Benefit, it doesn't cover configuration or deployment on VDI environments.
* x64 and x86 - Changing from a 32-bit OS to a 64-bit isn't supported. For more info, see [Windows 10 deployment scenario > In-place upgrade](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios#in-place-upgrade).

### Step 2: Apps

#### Security
Security clients (like antivirus, anti-malware, and anti-spam) are typically found on all PCs within an organization. Because these programs hook into the deeper levels of the OS, you may need to perform a compatibility assessment before starting any Windows 10 migrations. You may need to upgrade, reconfigure, or even replace Some software. Not performing this assessment can lead to:
* Native app compatibility checks failing and preventing an in-place upgrade from starting.
* Broken functionality in the security software.
* Instability after upgrading to Windows 10 (like crashing and reduced performance)

**Antivirus**

Assess current antivirus software. Windows 10 comes with Windows Defender Antivirus to protect devices from malware, viruses, and security threats. We recommend Windows Defender Antivirus. To enable Windows Defender Antivirus, see [Windows Defender Antivirus](windows10-enable-security-features.md#windows-defender-antivirus) and [Protect devices with Windows Defender Antivirus](https://go.microsoft.com/fwlink/?linkid=860254).

To learn about antivirus solutions from other providers, see [Consumer antivirus software providers for Windows](https://go.microsoft.com/fwlink/?linkid=67345).

#### App readiness
Each Windows 10 release provides improved app compatibility. However, some apps may not be compatible. Depending on the app, you may need to only do a simple upgrade or configuration update before upgrading to Windows 10. In other circumstances, you may need to remove an app entirely.

Be sure to assess business critical apps and understand the impact of upgrading to the next OS. Prioritize the workloads that impact the least number of people during deployment. 

See the following Upgrade Readiness resources to help with app inventory, driver compatibility issues, and usage information:
* [Manage Windows Upgrades with Upgrade Readiness](https://go.microsoft.com/fwlink/?linkid=860255) - Learn about the tools to help you plan and manage the upgrade process end to end, which allow you to adopt new Windows releases more quickly.
* [Configure Windows diagnostic data](https://go.microsoft.com/fwlink/?linkid=859970) - Find out about the importance of Windows diagnostic data and how Microsoft protects that data.

> [!NOTE]
> Upgrade Readiness may not be able to assess compatibility for custom and line-of-business (LOB) apps in an organization.

#### Language packs
In-place upgrades have have limitations when it comes to language packs. The language stays consistent throughout the upgrade. Verify the language version and make sure it stays consistent. For example, Windows 7 with English as the default won’t change when upgraded to Windows 10. For more info, see:
* [Default language pack on your OS](https://go.microsoft.com/fwlink/?linkid=860282)
* [Finding language packs on each Windows 10 deployment](https://go.microsoft.com/fwlink/?linkid=860283)

For a Microsoft 365 powered device, you'll also need to download Office 365 ProPlus language packs that applies to the client. These come in 32-bit (x86) or 64-bit (x64). A specific language must be installed as the default. You can install other languages later. For more info, see:
* [Choose between 64-bit or 32-bit version of Office](https://go.microsoft.com/fwlink/?linkid=862361) - Helps you decide which version of Office is right for you.
* [Language accessory pack for Office](https://go.microsoft.com/fwlink/?linkid=860280) - Follow the steps to install the language accessory pack for Office.
* [Add an additional language pack](https://go.microsoft.com/fwlink/?linkid=860281) - Get step-by-step info on adding a language or setting language preferences in Office.

### Step 3: Governance and business processes

#### Windows as a service
Windows 10 introduced the concept of Windows as a service. This greatly changes the frequency and style of updates to Windows. Instead of new versions being released every 3-5 years, a more incremental model is used where two smaller updates (Feature Updates) are released yearly. For more info, see:
* [Windows as a service on the Windows IT Pro Center](https://www.microsoft.com/itpro/windows-10/windows-as-a-service)
* [Overview of Windows as a service](https://go.microsoft.com/fwlink/?linkid=860288)
* [Update Windows 10 in the enterprise](https://go.microsoft.com/fwlink/?linkid=860285)

#### Pilot users and deployment rings
Be sure to have a pilot group of users selected from different parts of the business. If you have Microsoft 365 powered devices, Windows 10 and Office 365 ProPlus users should be in these deployment rings. This affects future Windows updates as well (including features and quality). You need to create and edit device collections by deployment rings to help minimize the effect on network bandwidth and simplify future updates. 

For the group of pilot users, create a device collection on Configuration Manager. The list of devices should correspond to the list of the first users upgraded to Windows 10. 

**Windows 10 deployment rings**

There are three servicing channels for OS deployment rings:
* Windows Insider Program - Provides organizations with the opportunity to test and provide feedback on features that are shipped in the next feature update.
* Semi-Annual Channel - Provides new functionality with twice-per-year feature update releases. Organizations can choose when to deploy updates from the Semi-Annual Channel.
* Long-Term Servicing Channel (LTSC) - Used for specialized devices and receives new feature releases about every three years.

For more info, see:
* [Windows Insider Program, Semi-Annual Channel, and Long-Term Servicing Channel](https://go.microsoft.com/fwlink/?linkid=860293)
* [Build deployment rings for Windows 10 updates](https://go.microsoft.com/fwlink/?linkid=860294)
* [Manage software updates using Intune in Azure Portal](https://docs.microsoft.com/intune/windows-update-for-business-configure)

**Office 365 ProPlus**

For Microsoft 365 powered devices, you must also be able to support the six-month update channel for both IT and business users. One way to do so is to have three groups:
* Current Channel
* Deferred Channel
* First-release for Deferred Channel

Each group has different configuration files, as users from the Current Channel are used as a pilot to test earlier updates. For more info, see:
* [Update process for Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860299)
* [Manage updates to Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860300)
* [Configure update settings for Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860301)
* [Update channels for Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860302)
* [Version and build numbers of update channel releases](https://go.microsoft.com/fwlink/?linkid=860304)

For more info, see [Phase 4: Office 365 ProPlus infrastructure for Microsoft 365 Enterprise](office365proplus-infrastructure.md).

## Phase 2: Testing phase
Once you've completed the scenarios and requirements in [Step 1: Consideration phase](#step-1-consideration-phase), you can move to this stage.
* [Networking](#step-1-networking)
* [Identity](#step-2-identity)
* [Client readiness](#step-3-client-readiness)
* [System Center Configuration Manager](#step-4-system-center-configuration-manager)
* [Diagnostic data](#step-5-diagnostic-data)

### Step 1: Networking
Ports to the client need to be opened for Office 365 ProPlus (for a Microsoft 365 powered device) and Configuration Manager. For more details about setting up your Microsoft 365 Enterprise networking infrastructure, see [Phase 1: Networking](networking-infrastructure.md).

When setting up your networking infrastructure as part your in-place upgrade, make sure you complete these steps:
1. Read the best practices for [network planning and improving migration performance for Office 365](http://go.microsoft.com/fwlink/?LinkId=733655).
2. [Plan for network devices that connect to Office 365 services](http://go.microsoft.com/fwlink/?LinkId=733652).
3. [Review network impact of directory synchronization](http://go.microsoft.com/fwlink/?LinkId=733652).
4. Calculate the number of clients to use per IP address and understand [Network Address Translation (NAT) support with Office 365](http://go.microsoft.com/fwlink/?LinkId=733653) and how it impacts the number of users and client devices you can serve with a single IP address.
5. If your organization restricts computers on your network from connecting to the Internet, you'll need to understand the [endpoints (fully qualified domain names (FQDNs), ports, URLs, IPv4, and IPv6 address ranges)](http://go.microsoft.com/fwlink/?LinkID=280129) that you should include in your outbound allow lists to ensure your computers can successfully use Office 365 services.
6. [Create domain name system records for Office 365 at any Domain Name System hosting provider](http://go.microsoft.com/fwlink/?LinkId=733656).
7. [Reduce mail exchange (MX) DNS record time to live (TTL) value](http://go.microsoft.com/fwlink/?LinkId=733656).

### Step 2: Identity
Intelligent security for Microsoft 365 Enterprise, in which the right users have access to the right resources with an appropriate level of access, begins with identity management. For more details about setting up your Microsoft 365 Enterprise identity infrastructure, see [Phase 2: Identity](identity-infrastructure.md).

When setting up your identity infrastructure as part of your in-place upgrade, make sure you complete these tasks:
1. [Add a domain and users to Office 365](http://go.microsoft.com/fwlink/?LinkID=526338).
2. [Install and run the Office 365 IdFix tool](http://go.microsoft.com/fwlink/?LinkId=733662), which scans your on-premises Active Directory environment and identifies problems that might impact directory synchronization and slow your migration to Office 365.
3. Configure Active Directory for directory synchronization with Office 365 and [integrate on-premises directories with Azure AD](http://go.microsoft.com/fwlink/?LinkId=733661).
4. [Prepare to provision users through directory synchronization to Office 365](http://go.microsoft.com/fwlink/?LinkId=733659).
5. Know the [prerequisites for Azure AD Connect](http://go.microsoft.com/fwlink/?LinkId=733663), then install and run the Azure AD Connect tool to synchronize your on-premises Active Directory to the Azure AD service used by Office 365.
6. Determine custom installation of Azure AD Connect (full version of SQL Server for directory synchronization, if required).
7. [Integrate your on-premises identities with Azure AD](http://go.microsoft.com/fwlink/?LinkID=733485).
8. [Sync a list of required attributes with AD Connect](https://go.microsoft.com/fwlink/?linkid=860363) to get all the features in Office 365 and Windows 10.
9. Activate Windows 10 Enterprise licenses, which are checked based on Azure AD credentials.

    This provides a systematic way to assign licenses to end users and groups in your organization. For more info, see [Windows 10 Subscription Activation](https://go.microsoft.com/fwlink/?linkid=860365) and [Deploy Windows 10 licenses](https://go.microsoft.com/fwlink/?linkid=860367).

### Step 3: Client readiness

#### System requirements for Office 365
Confirm that Windows 10 works with Office 365. Be sure you're using the latest OS version and browsers with Office 365 and have updated them with the latest service packs. For more info on Office requirements, see [System requirements for Office](http://go.microsoft.com/fwlink/?LinkID=394412).

### Step 4: System Center Configuration Manager
See [System Center Configuration Manager](#system-center-configuration-manager).

### Step 5: Diagnostic data
Microsoft uses diagnostic data to help keep Windows devices secure by identifying malware trends and other threats and to help us improve the quality of Windows and Microsoft services. You must ensure that the diagnostics service is enabled at a minimum level of Basic on all endpoints in your organization. **By default, this service is enabled and set to the Enhanced level.** However, it’s good practice to check and ensure that they are receiving sensor data. Setting levels through policies overrides device-level settings. 

**Windows 10 operating system diagnostic data levels**

You can configure your operating system diagnostic data settings using the management tools you’re already using, such as Group Policy, MDM, or Windows Provisioning. You can also manually change your settings using Registry Editor. Setting your diagnostic data levels through a management policy overrides any device level settings.

Use the appropriate value in the table below when you configure the management policy.

| Level | Data gathered | Value |
|:--- |:--- |:--- |
| Security | Security data only. | 0 |
| Basic | Security data, and basic system and quality data. | 1 |
| Enhanced | Security data, basic system and quality data, and enhanced insights and advanced reliability data. | 2 |
| Full | Security data, basic system and quality data, enhanced insights and advanced reliability data, and full diagnostics data. | 3 |

You can enable diagnostics data through these methods:
* Microsoft Intune - If you plan to use Intune to manage your devices, you can create a configuration policy to enable diagnostic data by configuring the <a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">SystemAllowTelemetry</a> system policy. For more info on setting up configuration policies, see [Manage settings and features on your devices with Microsoft Intune policies](https://aka.ms/intuneconfigpolicies).
* Registry Editor - You can use the Registry Editor to manually enable diagnostic data on each device in your organization, or write a script to edit the registry. If a management policy already exists, such as Group Policy or MDM, it will override this registry setting.
* Group Policy - If you do not plan to enroll devices in Intune, you can use a Group Policy object to set your organization’s diagnostic data level.
* Command prompt - You can set Windows 10 diagnostics data and service to automatically start with the command prompt. This method is best if you are testing the service on only a few devices. Enabling the service to start automatically with this command will not configure the diagnostic data level. If you have not configured a diagnostic data level using management tools, the service will operate with the default Enhanced level.

See [Configure Windows diagnostic data in your organization](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization) to learn more about Windows diagnostic data and how you can enable it based on the method that you choose.

## Phase 3: Deployment phase
When ready, complete these:
* [In-place upgrade to Windows 10 Enterprise](#31-in-place-upgrade-to-windows-10-enterprise)
* [Windows Defender Antivirus](#32-windows-defender-antivirus)

### Step 1: In-place upgrade to Windows 10 Enterprise
1. Integrate System Center Configuration Manager with Microsoft Deployment Tool.

    Be sure to use the Microsoft Deployment Toolkit (MDT) in conjunction with Configuration Manager when deploying an updated version of Windows 10. MDT brings Zero Touch Installation and Light Touch Installation enhancements to help with deployments at no cost to the customer. For more info, see:
    * [Download the latest MDT](https://go.microsoft.com/fwlink/?linkid=860465)
    * [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://go.microsoft.com/fwlink/?linkid=860466)

2. Prepare for zero touch installation.

    As part of zero touch installation, you are responsible for preparing the following:
    * Configuration Manager service accounts
    * Active Directory permissions
    * Source folder structure

    Then, [integrate Configuration Manager with MDT](https://go.microsoft.com/fwlink/?linkid=860035).

3. Create a custom Windows Preinstallation Environment boot image.

    Windows Preinstallation Environment (PE) is a pre-installation environment required for OS deployments. It’s used to prepare a client machine for Windows installation, to copy disk images from a network file server, and to initiate Windows Setup. It’s used for Windows 10 Enterprise editions. For more info, see:
    * [Overview of Windows PE](https://go.microsoft.com/fwlink/?linkid=860468)
    * [Windows PE features, hardware requirements, and limitations](https://go.microsoft.com/fwlink/?linkid=860469)
    * [Create a custom Windows PE boot image with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860470)

4. Add a Windows 10 OS upgrade image.

    You need to create a Windows 10 reference image with MDT (as needed). Reference images are the foundation of what each of the client machine’s OS looks like. The image should be in a separate folder located with the already-mounted ISO file. The task sequence looks for and then runs “setup.exe”. 

    Follow the steps to create and add a Windows 10 OS upgrade image on Configuration Manager:
    * [Create a Windows 10 reference image](https://go.microsoft.com/fwlink/?linkid=860500)
    * [Add a Windows 10 OS image using Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860501)

5. Create an app to deploy with Windows 10.

    For a Microsoft 365 powered device, you can deploy Office 365 ProPlus with Windows 10 Enterprise using Configuration Manager. You can also add other apps as needed.

    To deploy Office 365 ProPlus, follow the steps in [Phase 4: Office 365 ProPlus infrastructure for Microsoft 365 Enterprise](office365proplus-infrastructure.md). During this phase, make sure you complete these steps:
    
    1. Download the Office 2016 Deployment Tool (ODT) in conjunction with Configuration Manager to help with Office 365 ProPlus deployments. 
    2. Edit the configuration XML file to fit specific deployment needs (like version, language, and product element). 
    
    You can then create apps with Configuration Manager. For more info, see:
    * [Configuration options for ODT](https://go.microsoft.com/fwlink/?linkid=860504)
    * [Create apps in Configuration Manager](https://go.microsoft.com/fwlink/?linkid=761079)
    * [Deploy Office 365 ProPlus with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860506)

6. Add drivers to a Windows 10 deployment using Windows PE.

    Network drivers need to be created for both Windows PE and Windows 10 to connect deployment shares and storage drivers with local storage on a client computer. Use Configuration Manager to create these drivers required for deployment. For more info, see [Add drivers to a Windows 10 deployment with Windows PE using Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860036).

7. Create a task sequence.

    A task sequence (a collection of commands) is required for MDT Lite Touch Installation (LTI). You need to create and then edit the task sequence for optimal deployment experience. One of the configurations enable support for Unified Extensible Firmware Interface (UEFI). The UEFI environment is a minimal boot OS where devices are booted and the Windows 10 OS runs. For more info, see:
    * [Overview of Windows Boot Manager](https://go.microsoft.com/fwlink/?linkid=860696)
    * [Create the task sequence in Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860697)

8. Finalize the OS configuration for Windows 10 deployment.

    **To finalize the OS configuration**

    1. Enable MDT monitoring
    2. Create and share the Logs folder
    3. Configure the rules
    4. Distribute content to the distribution point (a server running Configuration Manager)
    5. Create a deployment for the task sequence

   For more info, see [Finalize OS configuration with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860697).

9. Deploy the Windows 10 Enterprise image to a UEFI machine.

    For more info, see [Deploy Windows 10 using Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860697).

10. Monitor the Windows 10 deployment.

    Use Configuration Manager and MDT to monitor your deployment. Deployment Workbench enables access to the computer remotely using the Diagnostics and Recovery Toolset (DaRT) (optional). Deployments can be monitored in Configuration Manager. For more info, see [Monitor the Windows 10 deployment with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860705).

### Step 2: Windows Defender Antivirus
See [Enable Windows 10 Enterprise security features > Windows Defender Antivirus](windows10-enable-security-features.md#windows-defender-antivirus)

-->
