---
title: Windows での Microsoft Defender オフライン
description: Microsoft Defender オフラインは、Microsoft Defender ウイルス対策アプリから直接使用できます。 また、ネットワークへの展開方法を管理することもできます。
keywords: scan, defender, offline
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.date: 07/28/2022
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 33f41114c0647de2987a5ed5abdaec4c885fcbfd
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67387443"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a>Microsoft Defender オフライン スキャンの結果を実行してレビューする

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

Microsoft Defender Offline は、信頼できる環境からスキャンを起動して実行できるマルウェア対策スキャン ツールです。 スキャンは通常の Windows カーネルの外部から実行されるため、マスター ブート レコード (MBR) に感染または上書きするウイルスやルートキットなど、Windows シェルをバイパスしようとするマルウェアをターゲットにすることができます。

Microsoft Defender Offline は、マルウェア感染が疑われる場合や、マルウェアの発生後にエンドポイントの完全なクリーンを確認する場合に使用できます。

Windows 10とWindows 11では、[Windows セキュリティ アプリ](microsoft-defender-security-center-antivirus.md)から直接ワンクリックで Microsoft Defender Offline を実行できます。 以前のバージョンの Windows では、ユーザーは Microsoft Defender Offline を起動可能なメディアにインストールし、エンドポイントを再起動し、起動可能なメディアを読み込む必要がありました。

## <a name="prerequisites-and-requirements"></a>前提条件と要件

Windows 10およびWindows 11の Microsoft Defender Offline には、Windows 10と同じハードウェア要件があります。

Windows 10要件とWindows 11要件の詳細については、次のトピックを参照してください。

- [ハードウェアの最小要件](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)
- [ハードウェア コンポーネントのガイドライン](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> Microsoft Defender Offline は、ARM プロセッサを搭載したマシンや Windows Server ストック キープ ユニットではサポートされていません。

エンドポイントから Microsoft Defender Offline を実行するには、ユーザーが管理者特権でログインしている必要があります。

## <a name="microsoft-defender-offline-updates"></a>Microsoft Defender オフライン更新プログラム

Microsoft Defender Offline では、エンドポイントで使用可能な最新の保護更新プログラムが使用されます。Microsoft Defender ウイルス対策が更新されるたびに更新されます。

> [!NOTE]
> オフライン スキャンを実行する前に、Microsoft Defender ウイルス対策保護の更新を試みる必要があります。 グループ ポリシーを使用して更新を強制するか、通常はエンドポイントに更新プログラムを展開するか、[Microsoft マルウェア プロテクション センター](https://www.microsoft.com/security/portal/definitions/adl.aspx)から最新の保護更新プログラムを手動でダウンロードしてインストールすることができます。

詳細については、 [Microsoft Defender ウイルス対策セキュリティ インテリジェンス更新プログラムの管理](manage-protection-updates-microsoft-defender-antivirus.md) に関するトピックを参照してください。

## <a name="usage-scenarios"></a>使用シナリオ

バージョン 1607 Windows 10では、手動でオフライン スキャンを強制できます。 または、Microsoft Defender Offline を実行する必要があるとWindows Defender判断した場合は、エンドポイントでユーザーにメッセージが表示されます。

オフライン スキャンを実行する必要性は、エンドポイントの管理に使用している場合は、Microsoft エンドポイント マネージャーでも明らかにされます。

このプロンプトは、次のような通知を介して発生する可能性があります。

:::image type="content" source="../../media/notification.png" alt-text="Microsoft Defender オフラインを実行する通知" lightbox="../../media/notification.png":::

ユーザーには、Windows Defender クライアント内でも通知されます。

Configuration Managerでは、[**監視>概要] > [セキュリティ] > [Endpoint Protection の状態] > System Center Endpoint Protection [状態] に移動することで、エンドポイントの状態を** 識別できます。

Microsoft Defender オフライン スキャンは、[**オフライン スキャンが必要**] として **[マルウェア修復の状態**] に表示されます。

:::image type="content" source="../../media/sccm-wdo.png" alt-text="Microsoft Defender オフラインのスキャンのインジケーター" lightbox="../../media/sccm-wdo.png":::

## <a name="configure-notifications"></a>通知を構成する

Microsoft Defender オフライン通知は、他の Microsoft Defender ウイルス対策通知と同じポリシー設定で構成されます。

Windows Defenderの通知の詳細については、「[エンドポイントに表示される通知を構成する](configure-notifications-microsoft-defender-antivirus.md)」トピックを参照してください。

## <a name="run-a-scan"></a>スキャンを実行する

> [!IMPORTANT]
> Microsoft Defender Offline を使用する前に、ファイルを保存し、実行中のプログラムをシャットダウンしてください。 Microsoft Defender オフライン スキャンの実行には約 15 分かかります。 スキャンが完了すると、エンドポイントが再起動されます。 スキャンは、通常の Windows オペレーティング環境の外部で実行されます。 ユーザー インターフェイスは、Windows Defenderによって実行される通常のスキャンとは異なって表示されます。 スキャンが完了すると、エンドポイントが再起動され、Windows は通常どおりに読み込まれます。

Microsoft Defender オフライン スキャンは、次の方法で実行できます。

- PowerShell
- Windows Management Instrumentation (WMI)
- Windows セキュリティ アプリ

### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a>PowerShell コマンドレットを使用してオフライン スキャンを実行する

次のコマンドレットを使用します。

```PowerShell
Start-MpWDOScan
```

[Microsoft Defender ウイルス対策で PowerShell を使用する方法の詳細については、「PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策](use-powershell-cmdlets-microsoft-defender-antivirus.md)コマンドレットと [Defender ウイルス対策コマンドレット](/powershell/module/defender/)を構成して実行する」を参照してください。

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a>Windows 管理命令 (WMI) を使用してオフライン スキャンを実行する

オフライン スキャンを実行するには [**、MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスを使用します。

次の WMI スクリプト スニペットは、Microsoft Defender オフライン スキャンを直ちに実行します。これにより、エンドポイントが再起動され、オフライン スキャンが実行され、Windows が再起動されて起動されます。

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start
```

詳細については、次を参照してください。

- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a>Windows Defender セキュリティ アプリを使用してオフライン スキャンを実行する

1. タスク バーのシールド アイコンをクリックするか、**Defender for Cloud** のスタート メニューを検索して、Windows セキュリティ アプリを開きます。

2. [ **ウイルス&脅威保護** ] タイル (または左側のメニュー バーのシールド アイコン) をクリックし、[ **詳細スキャン** ] ラベルをクリックします。

3. **Microsoft Defender オフライン スキャン** を選択し、[**今すぐスキャン**] をクリックします。

    > [!NOTE]
    > バージョン 1607 Windows 10では、オフライン スキャンは **Windows 設定** \> **更新プログラム&セキュリティ** \> **Windows Defender** またはWindows Defender クライアントから実行できます。

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
