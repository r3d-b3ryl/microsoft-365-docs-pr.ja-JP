---
title: 廃止 TLS 1.0 および 1.1 in Office 365 GCC High および DoD
description: Office 365 の GCC High および DoD 環境での TLS 1.1 および1.0 のサポートを中止するために、Microsoft が日付を移行する方法と、TLS 1.2 の使用を準備する方法について説明します。
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
ms.openlocfilehash: 76e9b203e58ba7fa23942ea42810456e3bee377d
ms.sourcegitcommit: 42b618231e9f608f3ae7226a313b0366601d0ea2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158882"
---
# <a name="deprecating-tls-10-and-11-in-office-365-gcc-high-and-dod"></a>廃止 TLS 1.0 および 1.1 in Office 365 GCC High および DoD

## <a name="summary"></a>概要

連邦リスクおよび承認管理プログラム (FedRAMP) に関する最新のコンプライアンス標準に準拠するために、Microsoft Office 365 で廃止トランスポート層セキュリティ (TLS) バージョン1.1 および1.0 を使用して、GCC High および DoD 環境を対象としています。 この変更は [、Office 365 で TLS 1.2 の必須の使用を準備するために、](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)Microsoft サポートによって既に発表されています。

データのセキュリティは重要であり、サービスの使用に影響を与える可能性がある変更については透過的にコミットされています。

[MICROSOFT TLS 1.0 の実装](https://support.microsoft.com/help/3117336)には既知のセキュリティ上の脆弱性はありませんが、FedRAMP 準拠の標準に対してコミットされたままになります。 そのため、1.1 年1月 2020 15 日から開始する GCC High および DoD 環境では、Office 365 の TLS および1.0 は廃止されます。 TLS 1.1 および1.0 の依存関係を削除する方法の詳細については、次のホワイトペーパーを参照してください。

[TLS 1.0 の問題を解決する](https://www.microsoft.com/download/details.aspx?id=55266)

TLS 1.1 および1.0 に対するこの変更の準備では、代わりに TLS バージョン1.2 を使用することをお勧めします。 詳細については、「 [Office 365 での TLS 1.2 の必須使用の準備](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)」を参照してください。

## <a name="more-information"></a>詳細情報

2020年1月15日から、GCC High および DoD 環境の Office 365 は TLS 1.1 および1.0 を廃止します。

2020年1月15日までに、クライアントサーバーとブラウザーサーバーのすべての組み合わせで TLS バージョン 1.2 (またはそれ以降のバージョン) を使用して、すべての接続が Office 365 サービスに問題が発生しないようにする必要があります。 この場合、クライアントサーバーとブラウザーサーバーの特定の組み合わせに対する更新が必要になることがあります。

2020年1月15日までに、TLS バージョン 1.2 (またはそれ以降のバージョン) に更新しない場合は、Office 365 に接続しようとすると問題が発生します。 また、解決策の一部として、TLS 1.2 (またはそれ以降のバージョン) に更新する必要があります。

次のクライアントは、TLS 1.2 を使用できないことがわかります。

- Android 4.3 およびそれ以前のバージョン
- Firefox 5.0 およびそれ以前のバージョン
- Windows 7 およびそれ以前のバージョンの Internet Explorer 8 ~ 10
- Windows Phone 8.0 の Internet Explorer 10
- Safari 6.0.4/OS X 10.8.4 以前のバージョン

Office 365 GCC High および DoD への継続的なアクセスを維持するように、クライアントを更新することをお勧めします。

Microsoft Online services への接続の現在の分析には、ほとんどのサービスとエンドポイントが TLS 1.1 および 1.0 1.0 1.1 の使用率が非常に低くなっていることが示されていますが、この変更に関する通知を提供して、影響を受けるクライアントまたはサーバーを必要に応じて更新できるようにします。 ハイブリッドシナリオまたは Active Directory フェデレーションサービス (AD FS) に対してオンプレミスのインフラストラクチャを使用している場合は、TLS 1.2 (またはそれ以降のバージョン) を使用する受信と送信の両方の接続をインフラストラクチャがサポートできることを確認してください。

TLS 1.2 を使用できないクライアントを使用した場合に発生する可能性のある停止に加えて、TLS 1.1 および1.0 を削除すると、次の Microsoft 製品を使用することができなくなります。

- Lync phone

## <a name="references"></a>関連情報

次のサポート記事には、クライアントが TLS 1.2 を使用していることを確認するためのガイダンスと参考情報が記載されています。

[Office 365 での TLS 1.2 の必須使用の準備](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
