---
title: 365 GCC High および DoD で TLS 1.0 Office 1.1 を無効にする
description: Microsoft が Microsoft 365 の GCC High および DoD 環境で TLS 1.1 および 1.0 のサポートを無効にする方法について説明します。
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: shmehta
appliesto:
- Office 365 Business
ms.openlocfilehash: a0b1fecc9991cd7ba4ac915d3d684d43714014af
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233753"
---
# <a name="disabling-tls-10-and-11-in-office-365-gcc-high-and-dod"></a>365 GCC High および DoD で TLS 1.0 Office 1.1 を無効にする

## <a name="summary"></a>要約

Federal Risk and Authorization Management Program (FedRAMP) の最新のコンプライアンス基準に準拠するために、Microsoft 365 for GCC High および DoD 環境ではトランスポート層セキュリティ (TLS) バージョン 1.1 および 1.0 を無効にします。 この変更は、Microsoft サポートを通じて以前に発表されたのが、Office [365 での TLS 1.2](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)の使用の準備です。

お客様のデータのセキュリティは重要であり、お客様によるサービスの使用に影響を与える可能性のある変更に関する透明性に取り組み、取り組み中です。

Microsoft [TLS 1.0 の](https://support.microsoft.com/help/3117336) 実装には既知のセキュリティの脆弱性はありませんが、FedRAMP コンプライアンス標準に引き続きコミットしています。 そのため、2020 年 1 月 15 日に、GCC High および DoD 環境の Office 365 で TLS 1.1 および 1.0 を無効にしました。 TLS 1.1 と 1.0 の依存関係を削除する方法については、次のホワイト ペーパーを参照してください。

[TLS 1.0 の問題の解決](https://www.microsoft.com/download/details.aspx?id=55266)

## <a name="more-information"></a>詳細情報

2020 年 1 月 15 日から、GCC High および DoD 環境の Office 365 は TLS 1.1 と 1.0 を廃止する予定です。

2020 年 1 月 15 日には、クライアント サーバーとブラウザー サーバーのすべての組み合わせで TLS バージョン 1.2 (以降のバージョン) を使用して、Office 365 サービスへの問題なくすべての接続を確立する必要があります。 これには、クライアント サーバーとブラウザー サーバーの特定の組み合わせに対する更新が必要な場合があります。

2020 年 1 月 15 日まで TLS バージョン 1.2 (以降のバージョン) に更新しない場合は、Office 365 に接続しようとするときに問題が発生します。 さらに、解決の一環として TLS 1.2 (以降のバージョン) に更新する必要があります。

クライアント コンピューターを更新して、365 GCC High および DoD への中断Officeアクセスを維持する必要があります。

TLS 1.0 または TLS 1.1 経由で Microsoft 365 API を呼び出すアプリケーションを更新して TLS 1.2 を使用する必要があります。 .NET 4.5 の既定値は TLS 1.1 です。 .NET 構成を更新するには、「クライアントでトランスポート層セキュリティ [(TLS) 1.2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)を有効にする方法」を参照してください。 詳細については、「Office [365 での TLS 1.2](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)の必須の使用の準備」を参照してください。

次のクライアント アプリケーションでは TLS 1.2 を使用できないことがわかっています。

- Android 4.3 およびそれ以前のバージョン
- Firefox 5.0 およびそれ以前のバージョン
- windows 7 Internet Explorer 8以前のバージョンでの Internet Explorer 8-10
- Internet Explorer 8.0 の Internet Explorer 10
- Safari 6.0.4/OS X 10.8.4 以前のバージョン

Microsoft Online サービスへの接続の現在の分析では、ほとんどのサービスとエンドポイントで TLS 1.1 と 1.0 の使用はほとんど見当たらされませんが、TLS 1.1 および 1.0 のサポートが終了する前に、影響を受けるクライアントまたはサーバーを必要に応じて更新できるよう、この変更に関する通知を提供しています。 ハイブリッド シナリオまたは Active Directory フェデレーション サービス (AD FS) にオンプレミスのインフラストラクチャを使用している場合は、TLS 1.2 (または以降のバージョン) を使用する受信接続と送信接続の両方をインフラストラクチャでサポートできる必要があります。

TLS 1.2 を使用できない一覧のクライアントを使用した場合に発生する可能性がある停止に加えて、TLS 1.1 と 1.0 を削除すると、次の Microsoft 製品を使用できません。

- Lync 電話

## <a name="references"></a>関連情報

次のサポート記事では、クライアントが TLS 1.2 を使用する場合に役立つガイダンスと参照情報について説明します。

[OFFICE 365 での TLS 1.2 の必須使用の準備](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
