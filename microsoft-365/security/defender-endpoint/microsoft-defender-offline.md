---
title: Microsoft Defender オフラインのWindows
description: アプリから直接Microsoft Defender オフラインを使用Windows Defender ウイルス対策できます。 ネットワークでの展開方法を管理できます。
keywords: スキャン、ディフェンダー、オフライン
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: ccb65b865afdf2a0ec0210c3593daee1cb5c09b6
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64476843"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a>Microsoft Defender オフライン スキャンの結果を実行してレビューする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender オフラインは、信頼できる環境からスキャンを起動して実行できるマルウェア対策スキャン ツールです。 スキャンは通常の Windows カーネルの外側から実行され、マスター ブート レコード (MBR) に感染または上書きするウイルスやルートキットなど、Windows シェルをバイパスしようとするマルウェアをターゲットにできます。

マルウェア感染がMicrosoft Defender オフライン疑われる場合や、マルウェアが発生した後にエンドポイントの完全なクリーンを確認する場合は、このツールを使用できます。

11 Windows 10および Windowsでは、Microsoft Defender オフラインアプリから直接 1 回のクリックでWindows セキュリティ[できます](microsoft-defender-security-center-antivirus.md)。 以前のバージョンの Windowsユーザーは、起動可能なメディアにMicrosoft Defender オフライン、エンドポイントを再起動し、起動可能なメディアを読み込む必要があります。

## <a name="prerequisites-and-requirements"></a>前提条件と要件

Microsoft Defender オフライン 11 Windows 10および Windows 11 のハードウェア要件は、ハードウェア要件と同Windows 10。

11 の要件Windows 10およびWindows詳細については、次のトピックを参照してください。

- [ハードウェアの最小要件](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)

- [ハードウェア コンポーネントのガイドライン](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> Microsoft Defender オフラインプロセッサを搭載したコンピューター、またはサーバーストックARMユニットではWindowsサポートされていません。

エンドポイントからMicrosoft Defender オフラインするには、管理者特権でログインする必要があります。

## <a name="microsoft-defender-offline-updates"></a>Microsoft Defender オフライン更新プログラム

Microsoft Defender オフラインエンドポイントで利用可能な最新の保護更新プログラムを使用します。エンドポイントが更新されるたびに更新Windows Defender ウイルス対策されます。

> [!NOTE]
> オフライン スキャンを実行する前に、Microsoft Defender AV 保護の更新を試みる必要があります。 グループ ポリシーを使用して更新を強制するか、通常はエンドポイントに更新プログラムを展開するか、最新の保護更新プログラムを手動でダウンロードしてインストール[Microsoft マルウェア プロテクション センター](https://www.microsoft.com/security/portal/definitions/adl.aspx)。

詳細については[、「セキュリティ インテリジェンスMicrosoft Defender ウイルス対策更新プログラムの管理」](manage-protection-updates-microsoft-defender-antivirus.md)を参照してください。

## <a name="usage-scenarios"></a>使用シナリオ

バージョン 1607 Windows 10では、手動でオフライン スキャンを強制できます。 または、Windows DefenderがMicrosoft Defender オフライン必要と判断した場合は、エンドポイントでユーザーにメッセージを表示します。

オフライン スキャンを実行する必要性は、エンドポイントの管理に使用している場合Microsoft エンドポイント マネージャーに表示されます。

このプロンプトは、次のような通知を介して実行できます。

:::image type="content" source="../../media/notification.png" alt-text="実行する通知Microsoft Defender オフライン" lightbox="../../media/notification.png":::

ユーザーには、クライアント内で通知Windows Defenderされます。

Configuration Manager で、エンドポイントの状態を識別するには、[監視] [概要] >[セキュリティ] > [状態> Endpoint Protection] > System Center Endpoint Protection **します**。

Microsoft Defender オフラインは[マルウェアの修復状態 **] で [** オフライン スキャンが必要 **] と表示されます**。

:::image type="content" source="../../media/sccm-wdo.png" alt-text="ユーザーのスキャンのインジケーター Microsoft Defender オフライン" lightbox="../../media/sccm-wdo.png":::

## <a name="configure-notifications"></a>通知の構成

Microsoft Defender オフラインは、他の Microsoft Defender AV 通知と同じポリシー設定で構成されます。

アプリの通知の詳細についてはWindows Defenderに表示される通知の構成[に関するトピックを参照](configure-notifications-microsoft-defender-antivirus.md)してください。

## <a name="run-a-scan"></a>スキャンを実行する

> [!IMPORTANT]
> このファイルを使用Microsoft Defender オフライン、ファイルを保存し、実行中のプログラムをシャットダウンしてください。 スキャンMicrosoft Defender オフライン実行に約 15 分かかります。 スキャンが完了すると、エンドポイントが再起動します。 スキャンは、通常のオペレーティング環境Windows実行されます。 ユーザー インターフェイスは、ユーザー インターフェイスによって実行される通常のスキャンとは異Windows Defender。 スキャンが完了すると、エンドポイントが再起動され、Windows読み込みされます。

次の方法でMicrosoft Defender オフラインスキャンを実行できます。

- PowerShell
- Windows Management Instrumentation (WMI)
- アプリWindows セキュリティアプリ



### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a>PowerShell コマンドレットを使用してオフライン スキャンを実行する

次のコマンドレットを使用します。

```PowerShell
Start-MpWDOScan
```

[PowerShell コマンドレットを](use-powershell-cmdlets-microsoft-defender-antivirus.md)構成して実行する方法の詳細については、「powerShell コマンドレットを構成して実行する Microsoft Defender ウイルス対策」および「[Defender Antivirus コマンドレット](/powershell/module/defender/)」を参照Microsoft Defender ウイルス対策。

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a>オフライン Windowsを実行するには、管理命令 (WMI) を使用します。

オフライン スキャンを [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) するには、MSFT_MpWDOScan クラスを使用します。

次の WMI スクリプト スニペットは直ちに Microsoft Defender オフライン スキャンを実行します。この場合、エンドポイントは再起動し、オフライン スキャンを実行し、再起動して、Windows に起動します。

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start
```

詳細については、以下を参照してください。

- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a>Windows Defender セキュリティ アプリを使用してオフライン スキャンを実行する

1. タスク バー Windows セキュリティシールド アイコンをクリックするか、Defender for Cloud のスタート メニューを検索して、アプリ **を開きます**。

2. [ウイルス **対策] &タイル** (または左側のメニュー バーのシールド アイコン) をクリックし、[高度なスキャン] **ラベルをクリック** します。

3. [スキャン **Microsoft Defender オフライン選択し、[** 今すぐスキャン] **をクリックします**。

    > [!NOTE]
    > バージョン Windows 10 1607  \> では、オフライン スキャンは Windows 設定 **Update &** \> セキュリティ Windows Defenderまたはクライアントから実行Windows Defender可能性があります。

## <a name="review-scan-results"></a>スキャン結果の確認

Microsoft Defender オフライン結果は、アプリの [スキャン履歴] セクションにWindows セキュリティ[されます](microsoft-defender-security-center-antivirus.md)。

## <a name="related-articles"></a>関連記事

- [スキャンと修復の結果をカスタマイズ、開始、および確認する](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
