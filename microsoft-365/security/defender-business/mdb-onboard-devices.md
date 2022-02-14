---
title: Microsoft Defender for Business へのオンボード デバイス (プレビュー)
description: Microsoft Defender for Business (プレビュー) のデバイスオンボーディング オプションについて説明します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 02/07/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 709af580211d999e5a2f4117a773686542d37160
ms.sourcegitcommit: 4c207a9bdbb6c8ba372ae37907ccefca031a49f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2022
ms.locfileid: "62465289"
---
# <a name="onboard-devices-to-microsoft-defender-for-business-preview"></a>Microsoft Defender for Business へのオンボード デバイス (プレビュー)

> [!IMPORTANT]
> Microsoft Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と IT パートナーに徐[](https://aka.ms/mdb-preview)々にロールアウトされます。 今後数週間以内に最初の一連の顧客とパートナーをオンボードし、一般提供に至るプレビューを拡大します。 プレビューは最初の一連 [のシナリオで](mdb-tutorials.md#try-these-preview-scenarios)起動し、定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 

Microsoft Defender for Business (プレビュー) では、組織のデバイスをオンボーディングするためのオプションがいくつか用意されています。 この記事では、オプションについて説明し、オンボーディングのしくみの概要について説明します。

## <a name="what-to-do"></a>操作

1. [オンボーディング方法について説明](#types-of-onboarding-methods)し、自動オンボーディングまたは手動オンボーディングを使用するかどうかを判断します。

2. 次のいずれかの操作を行います。

   - 自動オンボーディングを使用している場合は、「手順 [5: Microsoft Defender for Business (](mdb-configure-security-settings.md)プレビュー)でセキュリティ設定とポリシーを構成する」に進みます。
   - デバイスを手動でオンボーディングする場合は、[オンボーディング方法の種類[](#types-of-onboarding-methods)] でオンボーディング方法を選択し、その方法の指示に従います。
   - 既にデバイス を使用している場合はMicrosoft Intuneデバイスを使用[してオンボード デバイスに進Microsoft Intune](#onboard-devices-using-microsoft-intune)。

3. [新しくオンボードされたデバイスの](#run-a-detection-test) 検出テストを実行します。

4. [次の手順を参照してください](#next-steps)。 

この記事には、デバイスのオフ [ボード方法に関する情報も含まれています](#what-if-i-want-to-offboard-a-device)。

## <a name="types-of-onboarding-methods"></a>オンボーディングメソッドの種類

次の表では、プレビュー時に Defender for Business でサポートされるオンボーディング メソッドの種類について説明します。 
<br/><br/>

| オンボーディング方法  | 説明  |
|---------|---------|
| **自動オンボーディング**<br/>(*既にユーザーを使用しているお客様Microsoft エンドポイント マネージャー*) | Defender for Business (プレビュー) をMicrosoft エンドポイント マネージャー前に既にアプリケーションを使用していた場合、Defender for Business は検出します。 以前にオンボードされたデバイスに対して自動オンボーディング プロセスを使用Microsoft エンドポイント マネージャー。 <br/><br/>自動オンボーディングは、Defender for Business (プレビュー) と Microsoft エンドポイント マネージャー間の接続をセットアップし、デバイスを Defender for Business (プレビュー) にオンボードします。 このオプションを使用すると、デバイスを Defender for Business (プレビュー) にすばやく効率的にオンボードできます。 現在Windowsに登録されているすべてのデバイスMicrosoft エンドポイント マネージャー Defender for Business にオンボードされます。 <br/><br/>自動オンボーディングを選択した場合は、この記事の手順をスキップし、「手順 [5: Microsoft Defender for Business (プレビュー](mdb-configure-security-settings.md))でセキュリティ設定とポリシーを構成する」に進みます。  |
| **ローカル スクリプト**<br/>(*プレビュー中に推奨されます。一度にいくつかのデバイスをオンボーディングする場合に役立ちます*)  | プレビュー中に、macOS、Windows 10 または 11、および Linux デバイスでダウンロードして実行するスクリプトを使用して、Defender for Business (プレビュー) でデバイスをオンボードできます。 デバイス上でスクリプトを実行すると、Azure Active Directory (Azure AD) との信頼が作成され、デバイスがMicrosoft Intune。 このプロセスは、デバイスを [Microsoft Defender for Endpoint にオンボーディングするプロセスと似ています](../defender-endpoint/onboarding.md)。<br/><br/>このメソッドを使用するには、[ローカル スクリプトを使用してデバイスをオンボードする] に進[Microsoft 365 Defender。](#onboard-a-device-using-a-local-script-in-defender-for-business) |
| **Microsoft Intune** <br/>(*既にユーザーを使用しているMicrosoft Intune*) | Defender for Business (プレビュー) [をMicrosoft Intune](/mem/intune/fundamentals/what-is-intune)前に既にアプリを使用していた場合は、Microsoft Intuneを使用してデバイスをオンボードできます。 プレビュー中に、Microsoft Intuneを使用Windows、iOS、macOS、Linux、Android デバイスを Defender for Business (プレビュー) にオンボードできます。 <br/><br/>このメソッドを使用するには、「 [Intune でのデバイス登録」を参照してください](/mem/intune/enrollment/device-enrollment)。 |
| **グループ ポリシー** | [グループ ポリシー](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11)) は、グループ ポリシーの設定とグループ ポリシーの基本設定を使用して、ユーザーとコンピューターの管理構成を指定できるインフラストラクチャです。 グループ ポリシー オブジェクト (GPO) は、グループ ポリシー コンテナーとグループ ポリシー テンプレートで構成される論理オブジェクトです。 組織で既にグループ ポリシーを使用している場合は、GPO を作成し、Defender for Business (プレビュー) で組織のデバイスに適用できます。<br/><br/>この方法の詳細については、「グループ ポリシーを使用したオンボード [Windowsデバイス」を参照してください](../defender-endpoint/configure-endpoints-gp.md)。 | 
| **VDI オンボーディング スクリプト** | 組織が非永続的仮想デスクトップ インフラストラクチャ (VDI) デバイスを使用している場合は、ダウンロード可能なスクリプトを使用してそれらのエンドポイントをオンボードできます。 <br/><br/>この方法の詳細については、「オンボード非永続的 [VDI デバイス」を参照してください](../defender-endpoint/configure-endpoints-vdi.md)。  |


> [!TIP]
> デバイスのオンボード中に問題が発生した場合は、「 [Microsoft Defender for Business (プレビュー) のトラブルシューティング」を参照してください](mdb-troubleshooting.yml)。 

## <a name="onboard-a-device-using-a-local-script-in-defender-for-business"></a>Defender for Business でローカル スクリプトを使用してデバイスをオンボードする

1. ポータル () にMicrosoft 365 Defenderし[https://security.microsoft.com](https://security.microsoft.com)、サインインします。

2. ナビゲーション ウィンドウで、[設定 **Endpoints**] **を** > 選択し、[デバイスの管理] で [**オンボーディング]** **を選択します**。

3. オペレーティング システム (Windows 10 や **11** など) を選択し、[デバイスのオンボード] の [展開方法] セクションで、[ローカル スクリプト] **を選択します**。 

4. **[オンボーディング パッケージをダウンロードする]** を選択します。 オンボーディング パッケージをリムーバブル ドライブに保存することをお勧めします。

5. 次の記事のガイダンスに従います。

   - Windows: ローカル [スクリプトをWindowsデバイスのオンボード](../defender-endpoint/configure-endpoints-script.md#onboard-devices)
   - macOS デバイス: [macOS での Microsoft Defender for Endpoint の手動展開](../defender-endpoint/mac-install-manually.md#client-configuration)
   - Linux デバイス: [Linux で Microsoft Defender for Endpoint を手動で展開する](../defender-endpoint/linux-install-manually.md#client-configuration)

6. [デバイスの[検出テストを実行する](#run-a-detection-test)] に進Windowsします。

> [!IMPORTANT]
> 問題が発生してオンボーディング プロセスが失敗した場合は、「 [Microsoft Defender for Business (プレビュー) のトラブルシューティング」を参照してください](mdb-troubleshooting.yml)。

## <a name="onboard-devices-using-microsoft-intune"></a>デバイスを使用したオンボード Microsoft Intune

Defender for Business (プレビュー) をMicrosoft Intune前に既にアプリケーションを使用していた場合は、Microsoft Intuneを使用してデバイスをオンボードできます。 このヘルプについては、「デバイスの登録」[を参照Microsoft Intune](/mem/intune/enrollment/device-enrollment)。

## <a name="run-a-detection-test"></a>検出テストを実行する

デバイスを手動でWindowsした後、検出テストを実行して、Defender for Business (プレビュー) ですべてが正しく動作するようにすることができます。

1. デバイスでWindowsフォルダーを作成します。 `C:\test-MDATP-test`

2. 管理者としてコマンド プロンプトを開きます。

3. [コマンド プロンプト] ウィンドウで、次の PowerShell コマンドを実行します。

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

コマンドを実行すると、[コマンド プロンプト] ウィンドウが自動的に閉じます。 成功した場合、検出テストは完了としてマークされ、新しくオンボードされたデバイスの Microsoft 365 Defender ポータルに約 10 分で新しいアラートが表示されます。

## <a name="what-if-i-want-to-onboard-devices-gradually"></a>デバイスを段階的にオンボードする場合は、

組織のデバイスを段階的にオンボードする場合は、次の手順を実行します。

1. オンボードするデバイスのセットを識別します。

2. ポータル () にMicrosoft 365 Defenderし[https://security.microsoft.com](https://security.microsoft.com)、サインインします。

3. ナビゲーション ウィンドウで、[設定 **Endpoints**] **を** > 選択し、[デバイスの管理] で [**オンボーディング]** **を選択します**。

4. オペレーティング システム (Windows 10 **11 など) を選択** し、オンボーディング方法 (ローカル スクリプトなど) **を選択します**。 選択した方法のガイダンスに従います。

5. オンボードするデバイスのセットごとにこのプロセスを繰り返します。 

> [!TIP]
> デバイスをオンボードする度に同じオンボーディング パッケージを使用する必要はない。 たとえば、ローカル スクリプトを使用して一部のデバイスをオンボードし、後で別の方法を選択して、より多くのデバイスをオンボードできます。

## <a name="what-if-i-want-to-offboard-a-device"></a>デバイスのオフボードを行う場合は、

デバイスをオフボードする場合は、次の手順を実行します。

1. ポータル () にMicrosoft 365 Defenderサインイン[https://security.microsoft.com](https://security.microsoft.com)します。

2. ナビゲーション ウィンドウで、[エンドポイント **] を設定** し、[エンドポイント] **を選択します**。

3. [ **デバイスの管理] で**、[ **オフボード] を選択します**。

4. オペレーティング システム (Windows 10 および **11** など) を選択し、[デバイスのオフボード] の [展開方法] セクションで、[ローカル  スクリプト] を **選択します**。 

5. 確認画面で情報を確認し、[ダウンロード] を選択 **して** 続行します。

6. [オフ **ボード パッケージのダウンロード] を選択します**。 オフボード パッケージをリムーバブル ドライブに保存することをお勧めします。

7. オフボードする各デバイスでスクリプトを実行します。 

   このタスクに関するヘルプが必要ですか? 以下のリソースを参照してください。   

   - Windows: [ローカル スクリプトを使用Windowsオフボード デバイス](../defender-endpoint/configure-endpoints-script.md#offboard-devices-using-a-local-script)
   - macOS デバイス: [macOS でのアンインストール](../defender-endpoint/mac-resources.md#uninstalling)
   - Linux デバイス: [Linux でのアンインストール](../defender-endpoint/linux-resources.md#uninstall)

> [!IMPORTANT]
> デバイスをオフボードすると、デバイスは Defender for Business (プレビュー) へのデータの送信を停止します。 ただし、オフボード前に受信したデータは、最大 6 か月間保持されます。

## <a name="next-steps"></a>次の手順

次の手順に進みます。

- [手順 5: Microsoft Defender for Business でセキュリティ設定とポリシーを構成する (プレビュー)](mdb-configure-security-settings.md)

- [Microsoft Defender for Business の使用を開始する (プレビュー)](mdb-get-started.md) 