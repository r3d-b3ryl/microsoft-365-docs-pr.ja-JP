---
title: Microsoft Defender for Business にデバイスをオンボードする
description: Microsoft Defender for Business のデバイス オンボーディング オプションの詳細
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 03/14/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: c5de66418b242beb975cce0d6ece299753360c99
ms.sourcegitcommit: 8423f47fce3905a48db9daefe69c21c841da43a0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2022
ms.locfileid: "63504775"
---
# <a name="onboard-devices-to-microsoft-defender-for-business"></a>Microsoft Defender for Business にデバイスをオンボードする

> [!IMPORTANT]
> Microsoft Defender for Business は、2022 年 3 月 1 日からMicrosoft 365 Business Premium顧客に展開しています。[](../../business-premium/index.md) スタンドアロン サブスクリプションとしての Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と IT パートナーに徐 [々にロールアウト](https://aka.ms/mdb-preview) されます。 プレビューには最初 [の一連のシナリオが含まれています](mdb-tutorials.md#try-these-preview-scenarios)。定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 

Microsoft Defender for Business では、組織のデバイスをオンボーディングするためのオプションを複数選択できます。 この記事では、オプションについて説明し、オンボーディングのしくみの概要について説明します。

>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender for Business に関する短いアンケートをご覧ください</a>。 ご意見をお寄せください。
>

## <a name="get-the-device-onboarding-guide"></a>デバイスオンボーディング ガイドの取得

次のガイドと情報を使用して、組織に最適なオプションを選択します。

[:::image type="content" source="media/mdb-device-onboarding.png" alt-text="デバイスオンボーディング図のスクリーンショット":::](https://download.microsoft.com/download/4/d/2/4d2d8a86-2130-45b4-ba42-2997c854383a/MDB-DeviceOnboardingFlow-March2022.pdf) <br/>
[PDF](https://download.microsoft.com/download/4/d/2/4d2d8a86-2130-45b4-ba42-2997c854383a/MDB-DeviceOnboardingFlow-March2022.pdf) | [Visio](https://download.microsoft.com/download/4/d/2/4d2d8a86-2130-45b4-ba42-2997c854383a/MDB-DeviceOnboardingFlow-March2022.vsdx)

## <a name="what-to-do"></a>操作

1. [オンボーディング デバイスのオプションを確認し](#device-onboarding-methods)、方法を選択します。 

   - [デバイスに既に登録されているデバイスWindows自動オンボーディングを使用Microsoft エンドポイント マネージャー](#automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager)
   - [ローカル スクリプトを使用して、Windowsまたは macOS デバイスをオンボードする](#local-script-in-defender-for-business)
   - [モバイル Microsoft エンドポイント マネージャー、macOS、Windowsデバイスのオンボードに使用する](#microsoft-endpoint-manager)
   - [Microsoft Defender for Business セキュリティ構成を使用したデバイスオンボーディングの詳細](#microsoft-defender-for-business-security-configuration)

2. [新しくオンボードされたデバイス](#run-a-detection-test)で検出テストをWindowsします。

3. [次の手順を参照してください](#next-steps)。 

この記事には、デバイスの [オフボードに関する情報も含まれています](#offboarding-a-device)。

## <a name="device-onboarding-methods"></a>デバイスオンボーディングの方法

Defender for Business では、既に Microsoft エンドポイント マネージャー を使用している場合でも、簡単なオンボーディング エクスペリエンスが必要な場合でも、デバイスをオンボーディングする方法がいくつか用意されています。 デバイスを Defender for Business にオンボードするために最も一般的に使用される方法は次のとおりです。

- **デバイスに既に** Windowsされているデバイスの自動オンボーディングMicrosoft エンドポイント マネージャー。 自動オンボーディングは、Defender for Business と Microsoft エンドポイント マネージャー間の接続をセットアップし、Windows Defender for Business にデバイスをオンボードします。 このオプションを使用するには、デバイスが既にデバイスに登録されている必要エンドポイント マネージャー。 詳細については、「自動オンボーディング [」を参照してください](#automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager)。

- **ローカル スクリプトを使用** して、Windows macOS デバイスを Defender for Business に手動でオンボードします。 ローカル スクリプトを使用すると、一度に最大 10 台のデバイスをオンボードできます。 詳細については、「Defender [for Business のローカル スクリプト」を参照してください](#local-script-in-defender-for-business)。

- **Microsoft Intune**、**macOS Microsoft エンドポイント マネージャー** モバイル デバイスWindowsオンボーディングを行います。 デバイスをデバイスに登録エンドポイント マネージャー、デバイスを Defender for Business にオンボードできます。 [Microsoft 365 Business Premium](../../business-premium/index.md)ユーザーが既[にMicrosoft Intuneし](/mem/intune/fundamentals/what-is-intune)、[Microsoft Intuneモバイル デバイス](/mem/intune/enrollment/device-enrollment)管理の両方が現在、エンドポイント マネージャー。 このメソッドを使用するには、「Microsoft エンドポイント マネージャー」 [を参照してください](#microsoft-endpoint-manager)。

- **Microsoft Defender for Business セキュリティ構成** を使用して、Microsoft 365 Defender ポータル () でデバイスを直接オンボードします [https://security.microsoft.com](https://security.microsoft.com)。 このオプションを使用するには、特定の設定を構成して、Defender for Business とユーザー間の通信を容易エンドポイント マネージャー。 次に、各デバイスで選択、ダウンロード、および実行するパッケージを使用して、Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) のデバイスをオンボードします。 デバイスとデバイス間で信頼が確立Azure Active Directory (Azure AD)、Defender for Business セキュリティ ポリシーがデバイスにプッシュされます。 詳細については、「 [Microsoft Defender for Business セキュリティ構成」を参照してください](#microsoft-defender-for-business-security-configuration)。 

> [!IMPORTANT]
> 問題が発生してオンボーディング プロセスが失敗した場合は、「 [Microsoft Defender for Business のトラブルシューティング」を参照してください](mdb-troubleshooting.yml)。

## <a name="automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager"></a>デバイスに登録Windowsデバイスの自動オンボーディングMicrosoft エンドポイント マネージャー

自動オンボーディング オプションは、デバイスWindows適用されます。 自動オンボーディングは、次の条件が満たされている場合に使用できます。

- Defender for Business を使用するMicrosoft エンドポイント マネージャー前Microsoft Intune組織で、Microsoft Intune、モバイル デバイス管理 (MDM) が既に使用されている

- 既に、Windowsに登録されているデバイスエンドポイント マネージャー

Windowsデバイスが エンドポイント マネージャー に既に登録されている場合、Defender for Business は、Defender for Business のセットアップおよび構成中にそれらのデバイスを検出します。 すべてのデバイスまたは一部のデバイスに対して自動オンボーディングを使用Windowsされます。 すべてのデバイスを一度Windowsしたり、最初に特定のデバイスを選択したり、後でデバイスを追加したりできます。

> [!TIP]
> [すべてのデバイスが登録されている] オプションを選択することをお勧めします。 この方法で、Windowsデバイスが後で登録エンドポイント マネージャー、Defender for Business に自動的にオンボードされます。 また、エンドポイント マネージャー でセキュリティ ポリシーと設定を管理している場合は、Microsoft 365 Defender ポータルに切り替えてデバイス、ポリシー、設定を管理することをお勧めします。 詳細については、「セキュリティ ポリシーと [デバイスを管理する場所を選択する」を参照してください](mdb-configure-security-settings.md#choose-where-to-manage-security-policies-and-devices)。

自動オンボーディングの詳細については、「ウィザードを使用して [Microsoft Defender for Business](mdb-use-wizard.md) をセットアップする」の手順 2 を参照してください。

## <a name="local-script-in-defender-for-business"></a>Defender for Business のローカル スクリプト

ローカル スクリプトを使用して、ローカル デバイスと Mac Windowsオンボードできます。 デバイスでオンボード スクリプトを実行すると、Azure Active Directory との信頼が作成されます (その信頼が存在しない場合)、Microsoft エンドポイント マネージャー にデバイスを登録し (まだ登録されていない場合)、デバイスを Defender for Business にオンボードします。 このメソッドは、Defender for Business のデバイスをオンボーディングする場合に便利です。 最大 10 台のデバイスを一度にオンボードできます。

1. ポータル () にMicrosoft 365 Defenderし[https://security.microsoft.com](https://security.microsoft.com)、サインインします。

2. ナビゲーション ウィンドウで、[設定 **Endpoints**] **を** > 選択し、[デバイスの管理] で [**オンボーディング]** **を選択します**。

3. オペレーティング システム (Windows 10 **11** や **macOS** など) を選択し、[展開方法] セクションで [ローカル スクリプト]  **を選択します**。 

4. **[オンボーディング パッケージをダウンロードする]** を選択します。 オンボーディング パッケージをリムーバブル ドライブに保存することをお勧めします。 (**macOS** を選択した場合は、[インストール  パッケージをダウンロードしてリムーバブル デバイスに保存する] も選択します)。

5. 次の表のガイダンスに従います。

   | オペレーティング システム | Procedure |
   |---|---|
   | Windows | 1. デバイスWindows、構成パッケージの内容をデスクトップ フォルダーなどの場所に展開します。 という名前のファイルが必要です `WindowsDefenderATPLocalOnboardingScript.cmd`。 <br/><br/>2. 管理者としてコマンド プロンプトを開きます。<br/><br/>3. スクリプト ファイルの場所を入力します。 たとえば、ファイルをデスクトップ フォルダーにコピーした場合は、「: `%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd`」と入力し、Enter キーを押します (または **[OK] を選択します**)。<br/><br/>4. スクリプトの実行後、[検出テストの [実行] に進みます](#run-a-detection-test)。 |
   | macOS | 1. Mac コンピューターで、インストール パッケージをローカル ディレクトリ `wdav.pkg` に保存します。 <br/><br/>2. オンボーディング パッケージをインストール パッケージ `WindowsDefenderATPOnboardingPackage.zip` に使用したのと同じディレクトリに保存します。 <br/><br/>3. Finder を使用して保存した `wdav.pkg` 場所に移動し、開きます。<br/><br/>4. [ **続行] を** 選択し、ライセンス条項に同意し、メッセージが表示されたらパスワードを入力します。<br/><br/>5. Microsoft のドライバーのインストールを許可するように求めるメッセージが表示されます ("System Extension Blocked" または "Installation is on hold"、または両方)。 ドライバーのインストールを許可する必要があります。 インストールを許可するには、[Open **Security Preferences**] または [**Open System PreferencesSecurity** >  &**プライバシー**] を選択し、[許可] を選択 **します**。<br/><br/>6. Bash で次の Python コマンドを使用してオンボーディング パッケージを実行します。 `/usr/bin/python MicrosoftDefenderATPOnboardingMacOs.py` <br/><br/>7. デバイスが組織に関連付けられているか確認するには、Bash で次の Python コマンドを使用します。 `mdatp health --field org_id`<br/><br/>8. macOS 10.15 (Catalina) 以降を使用している場合は、デバイスを保護するために Defender for Business の同意を付与します。 「**System PreferencesSecurity** >  **&** **PrivacyFull** >  >  **Disk Access」に移動します**。  ロック アイコンを選択して変更を加えます (ダイアログ ボックスの下部)、Microsoft Defender for Business (または Defender for Endpoint) を選択します(表示されている場合)。 <br/><br/>9. デバイスがオンボードされているのを確認するには、Bash で次のコマンドを使用します。 `mdatp health --field real_time_protection_enabled`    |

## <a name="microsoft-endpoint-manager"></a>Microsoft エンドポイント マネージャー

Defender for Business を使用する前に エンドポイント マネージャー (Microsoft Intune とモバイル デバイス管理を含む) を既に使用していた場合は、引き続き エンドポイント マネージャー を使用して組織のデバイスをオンボードできます。 このエンドポイント マネージャー、iOS デバイスや Android デバイスを含むコンピューター、タブレット、電話をオンボードできます。

「[デバイスの登録」を参照Microsoft Intune](/mem/intune/enrollment/device-enrollment)。

## <a name="microsoft-defender-for-business-security-configuration"></a>Microsoft Defender for Business セキュリティ構成

> [!NOTE]
> デバイスとセキュリティ ポリシーを管理するためにエンドポイント マネージャーを既に使用している場合は、このメソッドをスキップし、代わりに「Microsoft エンドポイント マネージャー」[を](#microsoft-endpoint-manager)参照してください。

Microsoft Defender for Business セキュリティ構成は、 [Microsoft Defender for Endpoint (プレビュー) のセキュリティ管理と呼ばれる機能に基付けられています](/mem/intune/protect/mde-security-integration)。 これにより、デバイスを事前に完全に登録する必要なく、Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) で Defender for Business にデバイスをオンボードMicrosoft エンドポイント マネージャーできます。 

このメソッドを使用すると、デバイスをオンボードし、ウイルス対策ポリシーとファイアウォール ポリシーを Microsoft 365 Defenderできます ([https://security.microsoft.com](https://security.microsoft.com))。 これがすべて動作する方法を次に示します。

1. オンボード パッケージは、Microsoft 365 Defender ポータルからダウンロードし、デバイスでパッケージを実行して、それらのデバイスを Defender for Business にオンボードします。

2. パッケージを実行すると、各デバイス間の信頼が確立されます (信頼が存在しない場合)、Azure Active Directory (Azure AD)。 

3. デバイスは、エンドポイント マネージャー ID をAzure ADし、Defender for Business のセキュリティ ポリシーはデバイスにプッシュされます。

4. デバイスとポリシーは、Microsoft 365 Defender管理センター () のエンドポイント マネージャー表示できます[https://endpoint.microsoft.com](https://endpoint.microsoft.com)。

このオプションを使用するには、特定の設定を事前に構成する必要があります。 前提条件とサポートされているオペレーティング システムを含む詳細については、「Microsoft [Defender for Endpoint on devices with Microsoft エンドポイント マネージャー」 を参照してください](/mem/intune/protect/mde-security-integration)。

## <a name="run-a-detection-test"></a>検出テストを実行する

Defender for Business に Windowsデバイスをオンボードした後、Windows デバイスで検出テストを実行して、すべてが正しく動作するようにすることができます。

1. デバイスでWindowsフォルダーを作成します。 `C:\test-MDATP-test`

2. 管理者としてコマンド プロンプトを開きます。

3. [コマンド プロンプト] ウィンドウで、次の PowerShell コマンドを実行します。

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

コマンドを実行すると、[コマンド プロンプト] ウィンドウが自動的に閉じます。 成功した場合、検出テストは完了としてマークされ、新しくオンボードされたデバイスの新しいアラートが Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に約 10 分で表示されます。

## <a name="gradual-device-onboarding"></a>段階的なデバイスオンボーディング

組織のデバイスを段階的にオンボードできます。 *この段階的なデバイスオンボーディングを呼び出します*。 

1. オンボードするデバイスのセットを識別します。

2. ポータル () にMicrosoft 365 Defenderし[https://security.microsoft.com](https://security.microsoft.com)、サインインします。

3. ナビゲーション ウィンドウで、[設定 **Endpoints**] **を** > 選択し、[デバイスの管理] で [**オンボーディング]** **を選択します**。

4. オペレーティング システム (Windows 10 **11 など) を** 選択し、オンボーディング方法 (ローカル スクリプトなど) **を選択します**。 選択した方法のガイダンスに従います。

5. オンボードするデバイスのセットごとにこのプロセスを繰り返します。 

> [!TIP]
> デバイスをオンボードする度に同じオンボーディング パッケージを使用する必要はない。 たとえば、ローカル スクリプトを使用して一部のデバイスをオンボードし、後で別の方法を選択して、より多くのデバイスをオンボードできます。

## <a name="offboarding-a-device"></a>デバイスのオフボード

デバイスをオフボードする場合は、次のいずれかの手順を使用します。

| オペレーティング システム | Procedure |
|---|---|
| Windows | 1. ポータル () のMicrosoft 365 Defenderサインイン[https://security.microsoft.com](https://security.microsoft.com)します。<br/><br/>2. ナビゲーション ウィンドウで、[エンドポイント] を **設定し、[** エンドポイント] **を選択します**。<br/><br/>3. [デバイス **の管理] で、[****オフボード] を選択します**。<br/><br/>4. オペレーティング システム (**Windows 10 や 11** など) を選択し、[デバイスのオフボード] の [展開方法] セクションで、[ローカル スクリプト] を **選択します**。 <br/><br/>5. 確認画面で情報を確認し、[ダウンロード] を選択 **して続行します** 。<br/><br/>6. [オフ **ボード パッケージのダウンロード] を選択します**。 オフボード パッケージをリムーバブル ドライブに保存することをお勧めします。<br/><br/>7. オフボードする各デバイスでスクリプトを実行します。| 
| macOS | 1. **FinderApplications** >  に移動します。 <br/><br/>2. [Microsoft Defender for Business] を右クリックし、[ごみ箱に移動] **を選択します**。 <br/><br/>--- または --- <br/><br/> 次のコマンドを使用します。 `sudo '/Library/Application Support/Microsoft/Defender/uninstall/uninstall'`|

> [!IMPORTANT]
> デバイスをオフボードすると、デバイスは Defender for Business へのデータの送信を停止します。 ただし、オフボード前に受信したデータは、最大 6 か月間保持されます。

## <a name="next-steps"></a>次の手順

次の手順に進みます。

- [手順 5: Microsoft Defender for Business でセキュリティ設定とポリシーを構成する](mdb-configure-security-settings.md)

- [Microsoft Defender for Business の使用を開始する](mdb-get-started.md) 
