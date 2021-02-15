---
title: Microsoft 365 での TLS 1.0 および 1.1 の無効化
description: Microsoft 365 の TLS 1.0 および 1.1 の廃止と無効化について説明します。
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: fasqiu
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 669ab53739bfd108bdbe9077762272e6a4901865
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233099"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a>Microsoft 365 での TLS 1.0 および 1.1 の無効化

> [!IMPORTANT]
> 商用のお客様の場合、COVID-19 による TLS 1.0 および 1.1 の無効化を一時的に停止しました。 サプライ チェーンが調整され、特定の国がバックアップを開始すると、2020 年 10 月 15 日に TLS 1.2 実施ロールアウトが再開されました。 ロールアウトは、今後数週間から数か月の間続きます。

2018 年 10 月 31 日の現在、トランスポート層セキュリティ (TLS) 1.0 および 1.1 プロトコルは、Microsoft 365 サービスでは廃止されました。 エンドユーザーに対する影響は最小限です。 この変更は、2017 年 12 月に最初の公開発表が行われたので、2 年以上前から公開されています。 この記事は、Office 365 サービスに関連する Office 365 ローカル クライアントのみを対象としますが、Office および Office Online Server/Office Web Apps のオンプレミス TLS の問題にも適用できます。

SharePoint と OneDrive では、TLS 1.2 をサポートするために .NET を更新および構成する必要があります。 詳細については、「クライアントで [TLS 1.2 を有効にする方法」を参照してください](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)。

## <a name="office-365-and-tls-overview"></a>Office 365 と TLS の概要

クライアントOfficeは、WINDOWS Web サービス (WINHTTP) を使用して TLS プロトコルを通してトラフィックを送受信します。 ローカル Office Web サービスが TLS 1.2 を使用できる場合、クライアントは TLS 1.2 を使用できます。 TLS Office SSL プロトコルはオペレーティング システムの一部であり、クライアントに固有ではなOfficeされます。

### <a name="on-windows-8-and-later-versions"></a>バージョンWindows 8以降のバージョン

既定では、TLS 1.2 および 1.1 のプロトコルは、TLS 1.2 トラフィックを拒否するように構成されているネットワーク デバイスがない場合に使用できます。

### <a name="on-windows-7"></a>Windows 7 の場合

TLS 1.1 および 1.2 プロトコルは [、KB 3140245](https://support.microsoft.com/help/3140245) の更新なしでは使用できません。 この更新プログラムは、この問題に取り組み、次のレジストリ サブ キーを追加します。

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> この更新プログラムを適用していない Windows 7 ユーザーは、2018 年 10 月 31 日の時点で影響を受ける。 [KB 3140245](https://support.microsoft.com/help/3140245) には、TLS プロトコルを有効にするため WINHTTP 設定を変更する方法に関する詳細があります。

#### <a name="more-information"></a>詳細情報

使用できるネットワーク プロトコルは、サポート技術情報の記事で説明されている **DefaultSecureProtocols** レジストリ キーの値によって決されます。

|DefaultSecureProtocols 値|プロトコルの有効化|
|-|-|
|0x00000008|既定で SSL 2.0 を有効にします|
|0x00000020|既定で SSL 3.0 を有効にします|
|0x00000080|既定で TLS 1.0 を有効にします|
|0x00000200|既定で TLS 1.1 を有効にします|
|0x00000800|既定で TLS 1.2 を有効にします|

## <a name="office-clients-and-tls-registry-keys"></a>Officeクライアントと TLS レジストリ キー

KB [4057306 OFFICE 365 での TLS 1.2](https://support.microsoft.com/help/4057306)の必須使用の準備に関するページを参照してください。 これは IT 管理者向け一般的な記事であり、TLS 1.2 の変更に関する公式ドキュメントです。

次の表に、2018 年 10 月 31 日Office 365 クライアントの適切なレジストリ キー値を示します。

|2018 年 10 Office 365 サービスで有効になっているプロトコル|16 進数の値|
|-|-|
|TLS 1.0 + 1.1 + 1.2|0x00000A80|
|TLS 1.1 + 1.2|0x00000A00|
|TLS 1.0 + 1.2|0x00000880|
|TLS 1.2|0x00000800|

> [!IMPORTANT]
> SSL 2.0 および 3.0 プロトコルは使用しない **(DefaultSecureProtocols** キーを使用して設定できる)。 SSL 2.0 および 3.0 は、古い安全でないプロトコルと見なされます。 ベスト プラクティスは SSL 2.0 と SSL 3.0 の使用を終了する方法ですが、これを行う決定は最終的には、製品のニーズに最も合う内容によって異なります。 SSL 3.0 の脆弱性の詳細については [、KB 3009008 を参照](https://support.microsoft.com/help/3009008)してください。

プログラマ モードの既定の Windows 電卓を使用して、同じ参照レジストリ キー値を設定できます。 詳細については、Windows の WinHTTP で TLS 1.1 および TLS 1.2 を既定のセキュリティで保護されたプロトコルとして有効にする [KB 3140245 Update](https://support.microsoft.com/help/3140245)を参照してください。

Windows 7 更新プログラム ([KB 3140245)](https://support.microsoft.com/help/3140245)がインストールされている場合でもインストールされていない場合でも、DefaultSecureProtocols レジストリ サブキーは存在しなく、手動で追加するか、グループ ポリシー オブジェクト (GPO) を使用して追加する必要があります。 つまり、有効または制限されているセキュリティで保護されたプロトコルをカスタマイズする必要がない限り、このキーは必要ありません。 必要なのは、Windows 7 SP1 ([KB 3140245)](https://support.microsoft.com/help/3140245)更新プログラムのみです。

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a>TLS 1.2 をサポートするために .NET Framework を更新および構成する

TLS 1.0 または TLS 1.1 経由で Microsoft 365 API を呼び出すアプリケーションを更新して TLS 1.2 を使用する必要があります。 .NET 4.5 の既定値は TLS 1.1 です。 .NET 構成を更新するには、「クライアントでトランスポート層セキュリティ [(TLS) 1.2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)を有効にする方法」を参照してください。

## <a name="more-information"></a>詳細情報

詳細については、「Office [365 での TLS 1.2](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)の必須の使用の準備」を参照してください。
