---
title: Microsoft 365 GCC High および DoD で TLS 1.0 と 1.1 を無効にする
description: Microsoft 365の GCC High および DoD 環境で、Microsoft が TLS 1.1 および 1.0 のサポートを無効にする方法について説明します。
author: kccross
manager: laurawi
ms.localizationpriority: medium
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: krowley
appliesto:
- Office 365 Business
ms.openlocfilehash: bad0dc997f2c564670858d2ac35b2cd3177e0578
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/11/2022
ms.locfileid: "64760387"
---
# <a name="disabling-tls-10-and-11-in-microsoft-365-gcc-high-and-dod"></a>Microsoft 365 GCC High および DoD で TLS 1.0 と 1.1 を無効にする

## <a name="summary"></a>概要

連邦リスクと承認管理プログラム (FedRAMP) の最新のコンプライアンス基準に準拠するために、GCC High および DoD 環境のMicrosoft 365でトランスポート層セキュリティ (TLS) バージョン 1.1 および 1.0 を無効にしています。 この変更は、Office 365での [TLS 1.2 の必須使用の準備に関するMicrosoft サポートを](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)通じて以前に発表されました。

お客様のデータのセキュリティは重要であり、サービスの使用に影響を与える可能性のある変更に関する透明性に取り組んでいます。

[Microsoft TLS 1.0 実装](https://support.microsoft.com/help/3117336)には既知のセキュリティの脆弱性はありませんが、FedRAMP コンプライアンス標準に引き続き取り組んでいます。 そのため、2020 年 1 月 15 日に GCC High および DoD 環境のMicrosoft 365で TLS 1.1 と 1.0 を無効にしました。 TLS 1.1 と 1.0 の依存関係を削除する方法については、次のホワイト ペーパーを参照してください。

[TLS 1.0 の問題を解決する](https://www.microsoft.com/download/details.aspx?id=55266)

## <a name="more-information"></a>詳細

2020 年 1 月 15 日以降、GCC High および DoD 環境のMicrosoft 365では TLS 1.1 と 1.0 が無効になります。

2020 年 1 月 15 日までに、クライアント サーバーとブラウザー サーバーのすべての組み合わせで TLS バージョン 1.2 (またはそれ以降のバージョン) を使用して、すべての接続をMicrosoft 365に問題なく行えるようにする必要があります。 これには、クライアント サーバーとブラウザー サーバーの特定の組み合わせに対する更新が必要になる場合があります。

SharePoint と OneDrive の場合は、TLS 1.2 をサポートするように .NET を更新して構成する必要があります。 詳細については、「[クライアントで TLS 1.2 を有効にする方法](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)」 を参照してください。

クライアント コンピューターを更新して、Office 365 GCC High と DoD へのアクセスが中断されないようにする必要があります。

TLS 1.0 または TLS 1.1 経由で Microsoft 365 API を呼び出すアプリケーションを更新して、TLS 1.2 を使用する必要があります。 .NET 4.5 の既定値は TLS 1.1 になります。 .NET 構成を更新するには、「[クライアントでトランスポート層セキュリティ (TLS) 1.2 を有効にする方法](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)」を参照してください。 詳細については、「[Office 365 での TLS 1.2 の必須使用の準備](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)」 を参照してください。

次のクライアント アプリケーションでは TLS 1.2 を使用できないことがわかっています。

- Android 4.3 およびそれ以前のバージョン
- Firefox 5.0 およびそれ以前のバージョン
- Windows 7 上の Internet Explorer 8 ～ 10 およびそれ以前のバージョン
- Windows Phone 8.0 上の Internet Explorer 10
- Safari 6.0.4/OS X 10.8.4 以前のバージョン

Microsoft Online サービスへの接続の現在の分析では、ほとんどのサービスとエンドポイントに TLS 1.1 と 1.0 の使用状況がほとんどないことを示していますが、TLS 1.1 と 1.0 のサポートが終了する前に、影響を受けるクライアントまたはサーバーを必要に応じて更新できるように、この変更に関する通知を提供しています。 ハイブリッド シナリオまたはActive Directory フェデレーション サービス (AD FS) (AD FS) にオンプレミス インフラストラクチャを使用している場合は、TLS 1.2 (またはそれ以降のバージョン) を使用する受信接続と送信接続の両方をインフラストラクチャでサポートできることを確認します。

TLS 1.2 を使用できない一覧のクライアントを使用した場合に発生する可能性がある停止に加えて、TLS 1.1 と 1.0 を削除すると、次の Microsoft 製品を使用できなくなります。

- Lync Phone

## <a name="references"></a>関連情報

クライアントが TLS 1.2 を使用していることを確認するためのガイダンスと参照については、「[Office 365での TLS 1.2 の必須使用の準備](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)」を参照してください。
