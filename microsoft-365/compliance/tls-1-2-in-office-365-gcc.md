---
title: Microsoft 365 GCC High および DoD で TLS 1.0 および 1.1 を無効にする
description: Microsoft 365 の GCC High および DoD 環境での TLS 1.1 と 1.0 のサポートを無効にする方法について説明します。
author: kccross
manager: laurawi
localization_priority: Normal
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
ms.openlocfilehash: 16a02985107c5f578d6d6c21bf2efc6e80297951
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919343"
---
# <a name="disabling-tls-10-and-11-in-microsoft-365-gcc-high-and-dod"></a>Microsoft 365 GCC High および DoD で TLS 1.0 および 1.1 を無効にする

## <a name="summary"></a>要約

連邦リスクおよび承認管理プログラム (FedRAMP) の最新のコンプライアンス基準に準拠するために、Microsoft 365 for GCC High および DoD 環境では、トランスポート層セキュリティ (TLS) バージョン 1.1 および 1.0 を無効にします。 この変更は、Microsoft サポートを通じて [、365 での TLS 1.2](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)の必須使用の準備でOfficeされました。

データのセキュリティは重要であり、サービスの使用に影響を与える可能性のある変更に関する透明性に取り組む必要があります。

Microsoft [TLS 1.0](https://support.microsoft.com/help/3117336) の実装には既知のセキュリティの脆弱性は存在しますが、FedRAMP コンプライアンス標準に引き続き取り組む必要があります。 そのため、2020 年 1 月 15 日に GCC High 環境および DoD 環境で Microsoft 365 で TLS 1.1 および 1.0 を無効にしました。 TLS 1.1 と 1.0 の依存関係を削除する方法については、次のホワイト ペーパーを参照してください。

[TLS 1.0 の問題の解決](https://www.microsoft.com/download/details.aspx?id=55266)

## <a name="more-information"></a>詳細

2020 年 1 月 15 日から、GCC High 環境および DoD 環境の Microsoft 365 は TLS 1.1 と 1.0 を無効にします。

2020 年 1 月 15 日までには、クライアント サーバーとブラウザー サーバーのすべての組み合わせで TLS バージョン 1.2 (または以降のバージョン) を使用して、Microsoft 365 への問題なくすべての接続を確立する必要があります。 これには、クライアント サーバーとブラウザー サーバーの特定の組み合わせに対する更新が必要な場合があります。

SharePoint と OneDrive の場合は、TLS 1.2 をサポートするために .NET を更新して構成する必要があります。 詳細については、「クライアントで [TLS 1.2 を有効にする方法」を参照してください](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)。

クライアント コンピューターを更新して、365 GCC High および DoD に対する中断Officeアクセスを維持する必要があります。

TLS 1.0 または TLS 1.1 を使用して Microsoft 365 API を呼び出すアプリケーションを更新して、TLS 1.2 を使用する必要があります。 .NET 4.5 の既定値は TLS 1.1 です。 .NET 構成を更新するには、「クライアントでトランスポート層セキュリティ [(TLS) 1.2](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)を有効にする方法」を参照してください。 詳細については [、「365 の TLS 1.2](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)の必須使用の準備」を参照Officeしてください。

次のクライアント アプリケーションでは TLS 1.2 を使用できないことがわかっています。

- Android 4.3 およびそれ以前のバージョン
- Firefox 5.0 およびそれ以前のバージョン
- Internet Explorer 8 7 以前のバージョンの場合は、Internet Explorer 8-10 を使用します。
- Internet Explorer 10 on Windows Phone 8.0
- Safari 6.0.4/OS X 10.8.4 以前のバージョン

Microsoft Online サービスへの接続の現在の分析では、ほとんどのサービスとエンドポイントで TLS 1.1 と 1.0 の使用状況はほとんど表示されませんが、TLS 1.1 および 1.0 のサポートが終了する前に、必要に応じて影響を受けるクライアントまたはサーバーを更新できるよう、この変更に関する通知を提供しています。 ハイブリッド シナリオまたは Active Directory フェデレーション サービス (AD FS) にオンプレミス インフラストラクチャを使用している場合は、TLS 1.2 (または以降のバージョン) を使用する受信接続と送信接続の両方をインフラストラクチャでサポートできます。

TLS 1.2 を使用できない一覧のクライアントを使用する場合に発生する可能性がある機能停止に加えて、TLS 1.1 と 1.0 を削除すると、次の Microsoft 製品を使用できません。

- Lync 電話

## <a name="references"></a>関連情報

クライアントが TLS 1.2 を使用している場合のガイダンスと参照については、「Office [365 での TLS 1.2](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)の必須使用の準備」を参照してください。