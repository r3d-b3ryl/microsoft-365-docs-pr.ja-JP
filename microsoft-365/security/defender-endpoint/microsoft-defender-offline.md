---
title: Microsoft Defender オフラインのWindows 10
description: アプリから直接Microsoft Defender オフラインを使用Windows Defender ウイルス対策できます。 ネットワークでの展開方法を管理できます。
keywords: スキャン、ディフェンダー、オフライン
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 90e1c310952a1ef3fd19410f9d74b10591f0a18f
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58575518"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a>Microsoft Defender オフライン スキャンの結果を実行してレビューする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender オフラインは、信頼できる環境からスキャンを起動して実行できるマルウェア対策スキャン ツールです。 スキャンは通常の Windows カーネルの外部から実行され、マスター ブート レコード (MBR) に感染または上書きするウイルスやルートキットなど、Windows シェルをバイパスしようとするマルウェアをターゲットにできます。

マルウェア感染がMicrosoft Defender オフライン疑われる場合、またはマルウェアの発生後にエンドポイントの完全なクリーンを確認する場合は、このツールを使用できます。

このWindows 10、Microsoft Defender オフラインアプリから直接 1 回のクリックで実行Windows セキュリティ[できます](microsoft-defender-security-center-antivirus.md)。 以前のバージョンの Windowsユーザーは、起動可能なメディアにMicrosoft Defender オフラインをインストールし、エンドポイントを再起動し、起動可能なメディアを読み込む必要があります。

## <a name="prerequisites-and-requirements"></a>前提条件と要件

Microsoft Defender オフラインはWindows 10ハードウェア要件と同じWindows 10。 

要件の詳細についてはWindows 10トピックを参照してください。

- [ハードウェアの最小要件](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)

- [ハードウェア コンポーネントのガイドライン](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> Microsoft Defender オフラインプロセッサを搭載したコンピューター、またはサーバーストックARMユニットではWindowsサポートされていません。

エンドポイントからMicrosoft Defender オフラインするには、管理者特権でログインする必要があります。
 
## <a name="microsoft-defender-offline-updates"></a>Microsoft Defender オフライン更新プログラム

Microsoft Defender オフラインエンドポイントで利用可能な最新の保護更新プログラムを使用します。更新されるたびに更新Windows Defender ウイルス対策されます。 

> [!NOTE]
> オフライン スキャンを実行する前に、Microsoft Defender AV 保護の更新を試みる必要があります。 グループ ポリシーを使用して更新を強制するか、通常はエンドポイントに更新プログラムを展開するか、最新の保護更新プログラムを手動でダウンロードしてインストール[Microsoft マルウェア プロテクション センター。](https://www.microsoft.com/security/portal/definitions/adl.aspx)

詳細については[、「セキュリティ インテリジェンスMicrosoft Defender ウイルス対策更新プログラムの管理」](manage-protection-updates-microsoft-defender-antivirus.md)を参照してください。

## <a name="usage-scenarios"></a>使用シナリオ

バージョン 1607 Windows 10では、手動でオフライン スキャンを強制できます。 または、実行Windows Defender必要Microsoft Defender オフライン判断した場合は、エンドポイントでユーザーにメッセージを表示します。 

オフライン スキャンを実行する必要性は、エンドポイントの管理に使用している場合Microsoft エンドポイント マネージャーで表示されます。

このプロンプトは、次のような通知を介して実行できます。

:::image type="content" source="../../media/notification.png" alt-text="実行する通知Microsoft Defender オフライン。":::

ユーザーには、クライアント内で通知Windows Defenderされます。

Configuration Manager で、エンドポイントの状態を識別するには、[監視] > [セキュリティの概要] > [状態 **> Endpoint Protection]**> System Center Endpoint Protectionします。 

Microsoft Defender オフラインは[マルウェアの修復状態 **] で [** オフライン スキャンが必要]**と表示されます**。

:::image type="content" source="../../media/sccm-wdo.png" alt-text="Microsoft Defender オフラインが必要です。":::

## <a name="configure-notifications"></a>通知の構成

Microsoft Defender オフラインは、他の Microsoft Defender AV 通知と同じポリシー設定で構成されます。

[エンドポイントに表示される通知Windows Defender構成する] トピック[を参照](configure-notifications-microsoft-defender-antivirus.md)してください。

## <a name="run-a-scan"></a>スキャンを実行する 

> [!IMPORTANT]
> このファイルを使用Microsoft Defender オフライン、ファイルを保存し、実行中のプログラムをシャットダウンしてください。 スキャンMicrosoft Defender オフライン実行に約 15 分かかります。 スキャンが完了すると、エンドポイントが再起動します。 スキャンは、通常のオペレーティング環境Windows外で実行されます。 ユーザー インターフェイスは、ユーザー インターフェイスによって実行される通常のスキャンとは異Windows Defender。 スキャンが完了すると、エンドポイントが再起動され、Windows読み込みされます。

次のコマンドを使用Microsoft Defender オフラインスキャンを実行できます。

- PowerShell
- Windows Management Instrumentation (WMI)
- アプリWindows セキュリティアプリ



### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a>PowerShell コマンドレットを使用してオフライン スキャンを実行する

次のコマンドレットを使用します。

```PowerShell
Start-MpWDOScan
```

PowerShell[コマンドレットを](use-powershell-cmdlets-microsoft-defender-antivirus.md)構成して実行する方法の詳細については、「powerShell コマンドレットを使用して Microsoft Defender ウイルス対策 および[Defender](/powershell/module/defender/)コマンドレットを構成および実行する」を参照Microsoft Defender ウイルス対策。

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a>オフライン Windowsを実行するには、管理者管理命令 (WMI) を使用します。

オフライン スキャンを [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) するには、MSFT_MpWDOScan クラスを使用します。

次の WMI スクリプト スニペットは直ちに Microsoft Defender オフライン スキャンを実行します。この結果、エンドポイントが再起動され、オフライン スキャンが実行され、再起動して Windows に起動されます。

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start 
```

詳細については、以下を参照してください。
- [Windows DefenderWMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a>Windows Defender セキュリティ アプリを使用してオフライン スキャンを実行する

1. タスク バーのWindows セキュリティをクリックするか、Defender のスタート メニューを検索して、アプリを開 **きます**。

2. [ウイルス **対策] &タイル** (または左側のメニュー バーのシールド アイコン) をクリックし、[高度なスキャン] **ラベルをクリック** します。
    
3. [スキャン **Microsoft Defender オフライン選択し、[** 今すぐスキャン]**をクリックします**。

    > [!NOTE]
    > バージョン Windows 10 1607 では、オフライン スキャンは Windows 設定 Update   >  **&** セキュリティ &  >  **Windows Defender** または Windows Defender クライアントから実行できます。


## <a name="review-scan-results"></a>スキャン結果の確認

Microsoft Defender オフライン結果は、アプリの [スキャン履歴] セクションにWindows セキュリティ[されます](microsoft-defender-security-center-antivirus.md)。 


## <a name="related-articles"></a>関連記事

- [スキャンと修復の結果をカスタマイズ、開始、および確認する](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)