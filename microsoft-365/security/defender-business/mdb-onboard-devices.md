---
title: Microsoft Defender for Business へのオンボード デバイス (プレビュー)
description: Microsoft Defender for Business (プレビュー) のデバイスオンボーディング オプションについて説明します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/13/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 2b86836926546c8efdb17d760a406c0be31dc65d
ms.sourcegitcommit: 74f79aacb4ffcc6cb0e315239b1493324eabb449
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2021
ms.locfileid: "61507723"
---
# <a name="onboard-devices-to-microsoft-defender-for-business-preview"></a>Microsoft Defender for Business へのオンボード デバイス (プレビュー)

> [!IMPORTANT]
> Microsoft Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と[](https://aka.ms/mdb-preview)IT パートナーに徐々にロールアウトされます。 今後数週間以内に最初の一連の顧客とパートナーをオンボードし、一般提供に至るプレビューを拡大します。 プレビューは一連のシナリオで [起動](mdb-tutorials.md#try-these-preview-scenarios)し、定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 

Microsoft Defender for Business (プレビュー) では、会社のデバイスをオンボーディングするためのオプションがいくつか用意されています。 この記事では、オプションについて説明し、オンボーディングのしくみの概要について説明します。

## <a name="what-to-do"></a>操作

1. [オンボーディング方法について説明し](#types-of-onboarding-methods)、自動オンボーディングまたは手動オンボーディングを使用するかどうかを判断します。

2. 次のいずれかの操作を行います。

   - 自動オンボーディングを使用している場合は、「手順 [5: Microsoft Defender for Business (](mdb-configure-security-settings.md)プレビュー) でセキュリティ設定とポリシーを構成する」に進みます。
   - デバイスを手動でオンボーディングする場合は、[デバイスのオンボード] に進み、ローカル スクリプトを使用してデバイスをオンボード[Microsoft 365 Defender。](#onboard-a-device-using-a-local-script-in-defender-for-business)
   - 既にデバイスを使用している場合Microsoft Intuneに進み、デバイスを使用[してオンボード デバイスMicrosoft Intune。](#onboard-devices-using-microsoft-intune)

3. [新しくオンボードされたデバイスの](#run-a-detection-test) 検出テストを実行します。

4. [次の手順を参照してください](#next-steps)。 

この記事には、デバイスをオフ [ボードする方法に関する情報も含まれています](#what-if-i-want-to-offboard-a-device)。

## <a name="types-of-onboarding-methods"></a>オンボーディングメソッドの種類

次の表では、プレビュー時に Defender for Business でサポートされるオンボーディング メソッドの種類について説明します。 
<br/><br/>

| オンボーディング方法  | 説明  |
|---------|---------|
| **自動オンボーディング**<br/>(*既にユーザーを使用している* お客様Microsoft エンドポイント マネージャー ) | Defender for Business (プレビュー) をMicrosoft エンドポイント マネージャー前に既にアプリケーションを使用していた場合、Defender for Business は検出します。 以前にオンボードされたデバイスに対して自動オンボーディング プロセスを使用Microsoft エンドポイント マネージャー。 自動オンボーディングは、Defender for Business (プレビュー) と Microsoft エンドポイント マネージャー間の接続をセットアップし、デバイスを Defender for Business (プレビュー) にオンボードします。 このオプションを使用すると、デバイスを Defender for Business (プレビュー) にすばやく効率的にオンボードできます。<br/><br/>自動オンボーディング プロセスを選択した場合、そのデバイスに登録Microsoft エンドポイント マネージャー Defender for Endpoint にオンボードされます。 <br/><br/>自動オンボーディングを使用する場合は、この記事の手順を省略し、「手順 [5: Microsoft Defender for Business (プレビュー)](mdb-configure-security-settings.md)でセキュリティ設定とポリシーを構成する」に進みます。  |
| **ローカル スクリプト**<br/>(*プレビュー中に推奨されます。一度にいくつかのデバイスをオンボーディングする場合に役立ちます*)  | プレビュー中は、ローカル スクリプトを使用して Defender for Business (プレビュー) のデバイスをオンボードできます。 Microsoft Defender for Business (プレビュー) では、ダウンロード可能なスクリプトがホストされます。このスクリプトは、Windows 10または 11 台のデバイスで使用できます。 デバイス上でスクリプトを実行すると、Azure Active Directory (Azure AD) との信頼が作成され、デバイスがMicrosoft Intune。<br/><br/>このメソッドを使用する場合は、[ローカル スクリプトを使用してデバイスをオンボードする] に進[Microsoft 365 Defender。](#onboard-a-device-using-a-local-script-in-defender-for-business) |
| **Microsoft Intune** <br/>(*既にユーザーを使用しているお客様Microsoft Intune*) | Defender for Business (プレビュー) をMicrosoft Intune前に既にアプリケーションを使用していた場合は、Microsoft Intuneを使用してデバイスをオンボードできます。 たとえば、プレビュー中に iOS、macOS、Linux、Android デバイスを Defender for Business (プレビュー) にオンボードできます。 <br/><br/>このメソッドを使用する場合は [、「Intune でのデバイス登録」を参照してください](/mem/intune/enrollment/device-enrollment)。 |

> [!TIP]
> デバイスのオンボード中に問題が発生した場合は [、「Microsoft Defender for Business (プレビュー) のトラブルシューティング」を参照してください](mdb-troubleshooting.yml)。 

## <a name="onboard-a-device-using-a-local-script-in-defender-for-business"></a>Defender for Business でローカル スクリプトを使用してデバイスをオンボードする

1. ポータル ( ) にMicrosoft 365 Defender [https://security.microsoft.com](https://security.microsoft.com) し、サインインします。

2. ナビゲーション ウィンドウで、[エンドポイント] を選択 **設定** し、[デバイスの管理] で 、[オンボード  >  ]**を選択します**。 

3. [Windows 10 **11]** を選択し、[デバイスのオンボード] の **[展開** 方法] セクションで、[ローカル スクリプト]**を選択します**。 

4. **[オンボーディング パッケージをダウンロードする]** を選択します。 オンボーディング パッケージをリムーバブル ドライブに保存することをお勧めします。

5. 各デバイスで、次の手順を実行します。 

   1. ダウンロードした `WindowsDefenderATPOnboardingPackage.zip` ファイルをデバイスにコピーし、その内容を抽出します。 コンテンツをデバイスのデスクトップ フォルダーに **抽出** できます。
   
   2. 管理者としてコマンド プロンプトを開きます。
   
   3. [コマンド プロンプト] ウィンドウで、スクリプト ファイルの場所を入力します。 たとえば、ファイルをデスクトップ フォルダーにコピーした場合は、「Enter」キー `%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd` を押します。

6. [検出テスト [の実行] に進みます](#run-a-detection-test)。

> [!IMPORTANT]
> 問題が発生してオンボーディング プロセスが失敗した場合は [、「Microsoft Defender for Business (プレビュー) のトラブルシューティング」を参照してください](mdb-troubleshooting.yml)。

## <a name="onboard-devices-using-microsoft-intune"></a>デバイスを使用したオンボード Microsoft Intune

Defender for Business (プレビュー) をMicrosoft Intune前に既にアプリケーションを使用していた場合は、Microsoft Intuneを使用してデバイスをオンボードできます。 このヘルプについては、「デバイスの登録」[を参照Microsoft Intune。](/mem/intune/enrollment/device-enrollment)

## <a name="run-a-detection-test"></a>検出テストを実行する

デバイスを手動でオンボードした後、検出テストを実行して、Defender for Business (プレビュー) ですべてが正しく動作するようにすることができます。

1. デバイスで、フォルダーを作成します `C:\test-MDATP-test` 。

2. 管理者としてコマンド プロンプトを開きます。

3. [コマンド プロンプト] ウィンドウで、次の PowerShell コマンドを実行します。

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

コマンドを実行すると、[コマンド プロンプト] ウィンドウが自動的に閉じます。 成功した場合、検出テストは完了としてマークされ、新しくオンボードされたデバイスの Microsoft 365 Defender ポータルに約 10 分で新しいアラートが表示されます。

## <a name="what-if-i-want-to-offboard-a-device"></a>デバイスのオフボードを行う場合は、

デバイスをオフボードする場合は、次の手順を実行します。

1. ポータル ( ) にMicrosoft 365 Defenderサインイン [https://security.microsoft.com](https://security.microsoft.com) します。

2. ナビゲーション ウィンドウで、[エンドポイント] を選択 **設定** し、[エンドポイント]**を選択します**。

3. [ **デバイスの管理] で**、[ **オフボード] を選択します**。

4. [Windows 10 **11]** を選択し、[デバイスの **オフ** ボード] の [**展開** 方法] セクションで、[ローカル スクリプト]**を選択します**。 

5. 確認画面で情報を確認し、[ダウンロード] を選択 **して** 続行します。

6. zip 形式のフォルダーを、リムーバブル ドライブなどの場所に保存します。

7. 各デバイスで、次の手順を実行します。 

   1. ダウンロードした構成パッケージ ( `WindowsDefenderATPOffboardingPackage_valid_until_YYYY-MM-DD` ) をデバイスにコピーし、その内容を抽出します。 コンテンツをデバイスのデスクトップ フォルダーに **抽出** できます。 ( `YYYY-MM-DD` は、パッケージの有効期限を参照します)。

   2. 管理者としてコマンド プロンプトを開きます。

   3. [コマンド プロンプト] ウィンドウで、スクリプト ファイルの場所を入力します。 たとえば、ファイルをデスクトップ フォルダーにコピーした場合は、「Enter」キー `%userprofile%\Desktop\WindowsDefenderATPOffboardingPackage_valid_until_YYYY-MM-DD.cmd` を押します。

## <a name="next-steps"></a>次の手順

次の手順に進みます。

- [手順 5: Microsoft Defender for Business でセキュリティ設定とポリシーを構成する (プレビュー)](mdb-configure-security-settings.md)

- [Microsoft Defender for Business の使用を開始する (プレビュー)](mdb-get-started.md) 