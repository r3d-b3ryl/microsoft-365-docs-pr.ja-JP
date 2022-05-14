---
title: WindowsのMicrosoft Defender オフライン
description: Windows Defender ウイルス対策 アプリから直接Microsoft Defender オフラインを使用できます。 また、ネットワークへの展開方法を管理することもできます。
keywords: scan, defender, offline
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
ms.openlocfilehash: 690437de177ce1f6c466166970a8b7143d230916
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2022
ms.locfileid: "65415642"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a>Microsoft Defender オフライン スキャンの結果を実行してレビューする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

Microsoft Defender オフラインは、信頼できる環境からスキャンを起動して実行できるマルウェア対策スキャン ツールです。 スキャンは通常のWindows カーネルの外部から実行されるため、マスター ブート レコード (MBR) に感染または上書きするウイルスやルートキットなど、Windows シェルをバイパスしようとするマルウェアをターゲットにすることができます。

マルウェア感染が疑われる場合や、マルウェアの発生後にエンドポイントの完全なクリーンを確認する場合は、Microsoft Defender オフラインを使用できます。

Windows 10とWindows 11では、Windows セキュリティ アプリから直接ワンクリックで[Microsoft Defender オフライン](microsoft-defender-security-center-antivirus.md)を実行できます。 以前のバージョンのWindowsでは、ユーザーは起動可能なメディアにMicrosoft Defender オフラインをインストールし、エンドポイントを再起動し、起動可能なメディアを読み込む必要がありました。

## <a name="prerequisites-and-requirements"></a>前提条件と要件

Windows 10とWindows 11のMicrosoft Defender オフラインには、Windows 10と同じハードウェア要件があります。

Windows 10要件とWindows 11要件の詳細については、次のトピックを参照してください。

- [ハードウェアの最小要件](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)

- [ハードウェア コンポーネントのガイドライン](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> Microsoft Defender オフラインは、ARM プロセッサを搭載したマシンや、Windows Server Stock Keeping Units ではサポートされていません。

エンドポイントからMicrosoft Defender オフラインを実行するには、ユーザーが管理者特権でログインしている必要があります。

## <a name="microsoft-defender-offline-updates"></a>Microsoft Defender オフライン更新プログラム

Microsoft Defender オフラインは、エンドポイントで使用可能な最新の保護更新プログラムを使用します。Windows Defender ウイルス対策が更新されるたびに更新されます。

> [!NOTE]
> オフライン スキャンを実行する前に、Microsoft Defender AV 保護の更新を試みる必要があります。 グループ ポリシーを使用して更新を強制するか、通常はエンドポイントに更新プログラムを展開するか、[Microsoft マルウェア プロテクション センター](https://www.microsoft.com/security/portal/definitions/adl.aspx)から最新の保護更新プログラムを手動でダウンロードしてインストールすることができます。

詳細については、「[Microsoft Defender ウイルス対策 セキュリティ インテリジェンス更新プログラムの管理](manage-protection-updates-microsoft-defender-antivirus.md)」トピックを参照してください。

## <a name="usage-scenarios"></a>使用シナリオ

バージョン 1607 Windows 10では、手動でオフライン スキャンを強制できます。 または、Microsoft Defender オフラインを実行する必要があるとWindows Defender判断した場合は、エンドポイントでユーザーにメッセージが表示されます。

エンドポイントの管理に使用している場合は、オフライン スキャンを実行する必要もMicrosoft エンドポイント マネージャーで明らかにされます。

このプロンプトは、次のような通知を介して発生する可能性があります。

:::image type="content" source="../../media/notification.png" alt-text="Microsoft Defender オフラインを実行する通知" lightbox="../../media/notification.png":::

ユーザーには、Windows Defender クライアント内でも通知されます。

Configuration Managerでは、[**監視>概要] > [セキュリティ> Endpoint Protection状態> System Center Endpoint Protection状態]** に移動して、エンドポイントの状態を識別できます。

Microsoft Defender オフラインスキャンは、[**オフライン スキャンが必要**] として **[マルウェア修復の状態**] に表示されます。

:::image type="content" source="../../media/sccm-wdo.png" alt-text="Microsoft Defender オフラインのスキャンのインジケーター" lightbox="../../media/sccm-wdo.png":::

## <a name="configure-notifications"></a>通知を構成する

Microsoft Defender オフライン通知は、他の Microsoft Defender AV 通知と同じポリシー設定で構成されます。

Windows Defenderの通知の詳細については、「[エンドポイントに表示される通知を構成する](configure-notifications-microsoft-defender-antivirus.md)」トピックを参照してください。

## <a name="run-a-scan"></a>スキャンを実行する

> [!IMPORTANT]
> Microsoft Defender オフラインを使用する前に、ファイルを保存し、実行中のプログラムをシャットダウンしてください。 Microsoft Defender オフライン スキャンの実行には約 15 分かかります。 スキャンが完了すると、エンドポイントが再起動されます。 スキャンは、通常のWindowsオペレーティング環境の外部で実行されます。 ユーザー インターフェイスは、Windows Defenderによって実行される通常のスキャンとは異なって表示されます。 スキャンが完了すると、エンドポイントが再起動され、Windowsは正常に読み込まれます。

次のMicrosoft Defender オフライン スキャンを実行できます。

- PowerShell
- Windows Management Instrumentation (WMI)
- Windows セキュリティ アプリ



### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a>PowerShell コマンドレットを使用してオフライン スキャンを実行する

次のコマンドレットを使用します。

```PowerShell
Start-MpWDOScan
```

[Microsoft Defender ウイルス対策で PowerShell を使用する](use-powershell-cmdlets-microsoft-defender-antivirus.md)方法の詳細については、「PowerShell コマンドレットを使用してMicrosoft Defender ウイルス対策および [Defender ウイルス対策コマンドレット](/powershell/module/defender/)を構成して実行する」を参照してください。

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a>Windows管理命令 (WMI) を使用してオフライン スキャンを実行する

オフライン スキャンを実行するには [**、MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスを使用します。

次の WMI スクリプト スニペットは、Microsoft Defender オフライン スキャンをすぐに実行します。これにより、エンドポイントが再起動され、オフライン スキャンが実行され、再起動されてWindowsに起動されます。

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start
```

詳細については、次を参照してください。

- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a>Windows Defender セキュリティ アプリを使用してオフライン スキャンを実行する

1. タスク バーのシールド アイコンをクリックするか、Defender for Cloudのスタート メニューを検索して **、Windows セキュリティ アプリを** 開きます。

2. [ **ウイルス&脅威保護** ] タイル (または左側のメニュー バーのシールド アイコン) をクリックし、[ **詳細スキャン** ] ラベルをクリックします。

3. **Microsoft Defender オフラインスキャンを** 選択し、[**今すぐスキャン**] をクリックします。

    > [!NOTE]
    > バージョン 1607 Windows 10では、オフライン スキャンは **、Windows 設定** \> **Update & セキュリティ** \> **Windows Defender** またはWindows Defender クライアントから実行できます。

## <a name="review-scan-results"></a>スキャン結果を確認する

Microsoft Defender オフラインスキャン結果は、[Windows セキュリティ アプリの [スキャン履歴] セクションに](microsoft-defender-security-center-antivirus.md)一覧表示されます。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)

## <a name="related-articles"></a>関連記事

- [スキャンと修復の結果をカスタマイズ、開始、および確認する](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
