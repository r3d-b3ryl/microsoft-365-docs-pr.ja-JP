---
title: Microsoft Defender for Business にデバイスをオンボードする
description: Microsoft Defender for Business のデバイス オンボーディング オプションの詳細
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 03/09/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: a078b2a88fdde3af840cff64414fec0a712ae92e
ms.sourcegitcommit: 40f89c46032ea33de25417106f39cbeebef5a049
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2022
ms.locfileid: "63419306"
---
# <a name="onboard-devices-to-microsoft-defender-for-business"></a>Microsoft Defender for Business にデバイスをオンボードする

> [!IMPORTANT]
> Microsoft Defender for Business は、2022 年 3 月 1 日からMicrosoft 365 Business Premium顧客に展開しています。 スタンドアロン サブスクリプションとしての Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と IT パートナーに徐 [々にロールアウト](https://aka.ms/mdb-preview) されます。 プレビューには最初 [の一連のシナリオが含まれています](mdb-tutorials.md#try-these-preview-scenarios)。定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 

Defender for Business のデバイスオンボーディング エクスペリエンスは、Microsoft Defender for Endpoint で使用するプロセスに似たプロセスで構築されました。 次のビデオを見て、その動作を確認します。<br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

Microsoft Defender for Business では、組織のデバイスをオンボーディングするためのオプションを複数選択できます。 この記事では、オプションについて説明し、オンボーディングのしくみの概要について説明します。

> [!TIP]
> Defender for Endpoint でのデバイスオンボーディングの詳細については、「オンボード デバイス」を参照し、 [Microsoft Defender for Endpoint の機能を構成します](../defender-endpoint/onboard-configure.md)。

## <a name="what-to-do"></a>操作

1. オンボード デバイスのオプション [を確認し](#device-onboarding-methods)、次のいずれかの方法を選択します。 

   - [デバイスに登録Windowsデバイスの自動オンボーディングMicrosoft エンドポイント マネージャー](#automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager)
   - [ローカル デバイスと Mac Windowsローカル スクリプト](#local-script-in-defender-for-business)
   - [Microsoft エンドポイント マネージャー (Microsoft Intune)](#microsoft-endpoint-manager)
   - [Microsoft Defender for Business セキュリティ構成](#microsoft-defender-for-business-security-configuration)

2. [新しくオンボードされたデバイス](#run-a-detection-test)の検出テストをWindowsします。

3. [次の手順を参照してください](#next-steps)。 

この記事には、デバイス[の検出テスト](#run-a-detection-test)の実行とデバイスWindowsボードに関[する情報も含まれています](#offboarding-a-device)。

>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender for Business に関する短いアンケートをご覧ください</a>。 ご意見をお寄せください。
>

## <a name="device-onboarding-methods"></a>デバイスオンボーディングの方法

次の表では、デバイスを Defender for Business にオンボードするために最も一般的に使用される方法について説明します。 

| オンボーディング方法  | 説明  | OS |
|---------|---------|---------|
| **自動オンボーディング**<br/>(*既にユーザーを使用しているMicrosoft エンドポイント マネージャー*) | *Microsoft 365 Business Premiumユーザーは既にMicrosoft Intune、このオプションを使用できます*。 自動オンボーディングは、Defender for Business と Microsoft エンドポイント マネージャー間の接続をセットアップし、Windows Defender for Business にデバイスをオンボードします。 このオプションを使用するには、デバイスが既にデバイスに登録されている必要エンドポイント マネージャー。<br/><br/>詳細については、「自動オンボーディング [」を参照してください](#automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager)。 | Windows |
| **ローカル スクリプト** <br/> | このオプションを使用すると、個々のデバイスを Defender for Business に手動でオンボードできます。 ローカル スクリプトを使用すると、一度に最大 10 台のデバイスをオンボードできます。<br/><br/>詳細については、「Defender [for Business のローカル スクリプト」を参照してください](#local-script-in-defender-for-business)。 | Windows <br/>macOS |
| **Microsoft Intune** または **Microsoft エンドポイント マネージャー**<br/>(*ユーザーまたはユーザーが使用しているMicrosoft Intuneエンドポイント マネージャー*) | [Microsoft Intune](/mem/intune/fundamentals/what-is-intune)モバイル [デバイスの管理は](/mem/intune/enrollment/device-enrollment)、デバイスの一部エンドポイント マネージャー。 Microsoft 365 Business Premiumユーザーは既にMicrosoft Intune、このオプションを使用できます。<br/><br/>Defender for Business を使用する前にエンドポイント マネージャーを使用していた場合は、デバイスのオンボードと管理にエンドポイント マネージャーを続行できます。<br/><br/>このメソッドを使用するには、「Microsoft エンドポイント マネージャー」 [を参照してください](#microsoft-endpoint-manager)。 | Windows <br/>macOS<br/>iOS<br/>Android OS | 
| **Microsoft Defender for Business セキュリティ構成** <br/>(*ポータルMicrosoft 365 Defender使用*) | このオプションを使用するには、特定の設定を構成して、Defender for Business とユーザー間の通信を容易エンドポイント マネージャー。 次に、各デバイスでダウンロードして実行するパッケージを使用して、Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) のデバイスをオンボードします。 デバイスとデバイス間で信頼が確立Azure Active Directory (Azure AD)、Defender for Business セキュリティ ポリシーがデバイスにプッシュされます。<br/><br/>詳細については、「 [Microsoft Defender for Business セキュリティ構成」を参照してください](#microsoft-defender-for-business-security-configuration)。 | Windows <br/>macOS |

> [!IMPORTANT]
> 問題が発生してオンボーディング プロセスが失敗した場合は、「 [Microsoft Defender for Business のトラブルシューティング」を参照してください](mdb-troubleshooting.yml)。

## <a name="automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager"></a>デバイスに登録Windowsデバイスの自動オンボーディングMicrosoft エンドポイント マネージャー

自動オンボーディング オプションは、デバイスWindows適用されます。 Defender for Business を使用する前に組織が Microsoft Intune で Microsoft エンドポイント マネージャー、Microsoft Intune、またはモバイル デバイス管理 (MDM) を既に使用し、Windows デバイスが既に登録されている場合は、自動オンボーディングを使用できます。エンドポイント マネージャー。 

Windowsデバイスが エンドポイント マネージャー に既に登録されている場合、Defender for Business は、Defender for Business のセットアップおよび構成中にそれらのデバイスを検出します。 すべてのデバイスまたは一部のデバイスに対して自動オンボーディングを使用Windowsされます。 すべてのデバイスを一度Windowsしたり、最初に特定のデバイスを選択したり、後でデバイスを追加したりできます。

自動オンボーディングの詳細については、「ウィザードを使用して [Microsoft Defender for Business](mdb-use-wizard.md) をセットアップする」の手順 2 を参照してください。

## <a name="local-script-in-defender-for-business"></a>Defender for Business のローカル スクリプト

ローカル スクリプトを使用して、ローカル デバイスと Mac Windowsオンボードできます。 デバイスでオンボード スクリプトを実行すると、Azure Active Directory との信頼が作成されます (その信頼が存在しない場合)、Microsoft エンドポイント マネージャー にデバイスを登録し (まだ登録されていない場合)、デバイスを Defender for Business にオンボードします。 このメソッドは、Defender for Business のデバイスをオンボーディングする場合に便利です。 最大 10 台のデバイスを一度にオンボードできます。

1. ポータル () にMicrosoft 365 Defenderし[https://security.microsoft.com](https://security.microsoft.com)、サインインします。

2. ナビゲーション ウィンドウで、[設定 **Endpoints**] **を** > 選択し、[デバイスの管理] で [**オンボーディング]** **を選択します**。

3. オペレーティング システム (Windows 10 および **11** など) を選択し、[デバイスのオンボード] の [展開方法] セクションで、[ローカル  スクリプト] を **選択します**。 

4. **[オンボーディング パッケージをダウンロードする]** を選択します。 オンボーディング パッケージをリムーバブル ドライブに保存することをお勧めします。

5. 次の記事のガイダンスに従います。

   - Windows: [ローカル スクリプトをWindowsデバイスをオンボードする](../defender-endpoint/configure-endpoints-script.md#onboard-devices)
   - macOS デバイス: [macOS での Microsoft Defender for Endpoint の手動展開](../defender-endpoint/mac-install-manually.md#client-configuration)

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

デバイスをオフボードする場合は、次の手順を実行します。

1. ポータル () にMicrosoft 365 Defenderサインイン[https://security.microsoft.com](https://security.microsoft.com)します。

2. ナビゲーション ウィンドウで、[エンドポイント] を **設定** し、[エンドポイント] **を選択します**。

3. [ **デバイスの管理] で**、[ **オフボード] を選択します**。

4. オペレーティング システム (Windows 10 および **11** など) を選択し、[デバイスのオフボード] の [展開方法] セクションで、[ローカル  スクリプト] **を選択します**。 

5. 確認画面で情報を確認し、[ダウンロード] を選択 **して** 続行します。

6. [オフ **ボード パッケージのダウンロード] を選択します**。 オフボード パッケージをリムーバブル ドライブに保存することをお勧めします。

7. オフボードする各デバイスでスクリプトを実行します。 このタスクに関するヘルプが必要ですか? 以下のリソースを参照してください。   

   - Windows: [ローカル スクリプトをWindowsオフボード デバイス](../defender-endpoint/configure-endpoints-script.md#offboard-devices-using-a-local-script)
   - macOS デバイス: [macOS でのアンインストール](../defender-endpoint/mac-resources.md#uninstalling)

> [!IMPORTANT]
> デバイスをオフボードすると、デバイスは Defender for Business へのデータの送信を停止します。 ただし、オフボード前に受信したデータは、最大 6 か月間保持されます。

## <a name="next-steps"></a>次の手順

次の手順に進みます。

- [手順 5: Microsoft Defender for Business でセキュリティ設定とポリシーを構成する](mdb-configure-security-settings.md)

- [Microsoft Defender for Business の使用を開始する](mdb-get-started.md) 
