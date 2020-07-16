---
title: Office 365 の TLS 1.0 および1.1の 廃止
description: Office 365 の TLS 1.0 および1.1 が廃止されたことについて説明します。
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: shmehta
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 270d04974cec9c36fa31a77bda401375fdac0471
ms.sourcegitcommit: 94f2f8e3e6bc3946d8b3cf798b3eb77a49ffd12a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "45148149"
---
# <a name="tls-10-and-11-deprecation-for-office-365"></a>Office 365 の TLS 1.0 および1.1の 廃止
> [!IMPORTANT]
> 商用のお客様のために TLS 1.0 および1.1 の推奨されていない強制を一時的に停止していますが、サプライチェーンが調整され、特定の国が開いたときに、10月15日の2020を開始するように TLS の強制をリセットしています。 

2018年10月31日の時点で、Office 365 サービスのトランスポート層セキュリティ (TLS) 1.0 および1.1 プロトコルは使用されなくなりました。 エンドユーザーへの影響は最小限に抑える必要があります。 この変更は、2年以上にわたって公表されており、最初のパブリックアナウンスは2017年12月に行われています。 この記事は、office 365 のローカルクライアントを Office 365 サービスに関連するものだけを対象としていますが、Office および Office Online Server/Office Web Apps のオンプレミスの TLS の問題にも適用できます。

## <a name="office-and-tls-overview"></a>Office と TLS の概要

Office クライアントは、Windows web サービス (WINHTTP) に依存して、TLS プロトコル経由のトラフィックの送受信を行います。 ローカルコンピューターの web サービスが TLS 1.2 を使用できる場合、Office クライアントは TLS 1.2 を使用できます。 Tls および SSL プロトコルはオペレーティングシステムの一部であり、Office クライアントに固有ではないため、すべての Office クライアントで TLS プロトコルを使用できます。

### <a name="on-windows-8-and-later-versions"></a>Windows 8 以降のバージョン

既定では、TLS 1.2 トラフィックを拒否するようにネットワークデバイスが構成されていない場合、TLS 1.2 および1.1 プロトコルが使用できます。

### <a name="on-windows-7"></a>Windows 7

TLS 1.1 および1.2 プロトコルは、 [KB 3140245](https://support.microsoft.com/help/3140245)の更新プログラムがないと使用できません。 この更新プログラムはこの問題に対処し、次のレジストリサブキーを追加します。

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> この更新プログラムをインストールしていない Windows 7 ユーザーは、2018年10月31日の時点で影響を受けます。 [KB 3140245](https://support.microsoft.com/help/3140245)は、WINHTTP 設定を変更して TLS プロトコルを有効にする方法についての詳細を示しています。

#### <a name="more-information"></a>詳細情報

KB の記事に記載されている**Defaultsecureprotocols**レジストリキーの値は、どのネットワークプロトコルを使用できるかを決定します。

|DefaultSecureProtocols の値|プロトコルの有効化|
|-|-|
|0x00000008|既定で SSL 2.0 を有効にします|
|0x00000020|既定で SSL 3.0 を有効にします|
|0x00000080|既定で TLS 1.0 を有効にします|
|0x00000200|既定で TLS 1.1 を有効にします|
|0x00000800|既定で TLS 1.2 を有効にします|

## <a name="office-clients-and-tls-registry-keys"></a>Office クライアントと TLS レジストリキー

[Office 365 で TLS 1.2 を必須で使用するための準備として、KB 4057306](https://support.microsoft.com/help/4057306)を参照することができます。 これは IT 管理者向けの一般的な記事であり、TLS 1.2 の変更に関する公式ドキュメントです。

次の表に、2018年10月31日以降の Office 365 クライアントの適切なレジストリキー値を示します。

|2018年10月31日以降の Office 365 サービスの有効化プロトコル|16進値|
|-|-|
|TLS 1.0 + 1.1 + 1.2|0x00000A80|
|TLS 1.1 + 1.2|0x00000A00|
|TLS 1.0 + 1.2|0x00000880|
|TLS 1.2|0x00000800|

> [!IMPORTANT]
> SSL 2.0 および3.0 プロトコルを使用することはお勧めしません。これは、 **Defaultsecureprotocols**キーを使用して設定することもできます。 SSL 2.0 および3.0 は、非推奨プロトコルと見なされます。 最善の方法は、SSL 2.0 および SSL 3.0 の使用を終了することですが、これを最終的に決定することは、製品のニーズに最も適した内容によって決まります。 SSL 3.0 の脆弱性の詳細については、「 [KB 3009008](https://support.microsoft.com/help/3009008)」を参照してください。

既定の Windows 電卓をプログラマモードで使用して、同じ参照レジストリキーの値を設定することができます。 詳細については、「 [KB 3140245 更新プログラム」を参照して、Windows の WinHTTP で既定のセキュリティ保護されたプロトコルとして tls 1.1 と tls 1.2 を有効](https://support.microsoft.com/help/3140245)にします。

Windows 7 更新プログラム ([KB 3140245](https://support.microsoft.com/help/3140245)) がインストールされているかどうかにかかわらず、DefaultSecureProtocols のレジストリサブキーは存在しないため、手動で追加するか、グループポリシーオブジェクト (GPO) を使用して追加する必要があります。 つまり、有効または制限のあるセキュリティで保護されたプロトコルをカスタマイズする必要がない場合は、このキーは必要ありません。 Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) の更新プログラムのみが必要です。
