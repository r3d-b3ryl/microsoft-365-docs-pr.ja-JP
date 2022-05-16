---
title: 'MTA-STS を使用したメール フローの強化 '
f1.keywords:
- NOCSH
ms.author: v-bshilpa
author: Benny-54
manager: serdars
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: high
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
description: MTA-STS を使用してメール フローを強化する方法について説明します。
ms.openlocfilehash: 735cce96c61a2083b8f0785ace49a5b199790989
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2022
ms.locfileid: "65415191"
---
# <a name="enhancing-mail-flow-with-mta-sts"></a>MTA-STS を使用したメール フローの強化

[SMTP MTA Strict Transport Security](https://datatracker.ietf.org/doc/html/rfc8461) (MTA-STS) 標準のサポートが Exchange Online に追加されます。 この標準は、メール サーバー間の接続に TLS が常に使用されるようにするために開発されました。 また、受信側のサーバーに信頼できる証明書があることを検証するためにサーバーを送信する方法も提供されます。 TLS が提供されていないか、証明書が有効でない場合、送信者はメッセージの配信を拒否します。 これらの新しいチェックにより、SMTP の全体的なセキュリティが向上し、中間者攻撃から保護されます。

MTA-STS は、受信保護と送信保護の 2 つのシナリオに分類できます。受信は、Exchange Online でホストされているドメインの保護を MTA-STS と送信でカバーし、Exchange Online が MTA-STS で保護されたドメインにメールを送信する場合に実行される MTA-STS 検証を対象とします。

## <a name="outbound-protection"></a>送信保護

Exchange Online から MTA-STS で保護された受信者に送信されるすべてのメッセージは、MTA-STS 標準によって設定されたこれらの追加のセキュリティ チェックを使用して検証されます。 管理者が適用するために必要な操作はありません。 送信の実装では、MTA-STS ポリシーを介して受信者ドメイン所有者の希望を尊重します。 MTA-STS は、Exchange Onlineのセキュリティ インフラストラクチャの一部を形成するため、(他のコア SMTP 機能と同様に) 常にオンになります。

## <a name="inbound-protection"></a>受信保護

ドメイン所有者は、MX レコードが Exchange Online を指す場合、MTA-STS を使用してドメインに送信されたメールを保護するために対処できます。 MX レコードが中間サード パーティのサービスを指す場合は、MTA-STS の要件が満たされていることを確認し、指示に従う必要があります。

ドメインに対して MTA-STS が設定されると、MTA-STS をサポートする送信者から送信されたすべてのメッセージが、セキュリティで保護された接続を確保するために標準でレイアウトされた検証を実行します。 MTA-STS をサポートしていない送信者からメールを受信した場合でも、追加の保護なしでメールが配信されます。 同様に、まだ MTA-STS を使用していないものの送信者がメッセージをサポートしている場合、メッセージが中断されることはありません。 メッセージが配信されない唯一のシナリオは、MTA-STS と MTA-STS 検証を使用した両側で失敗した場合です。

## <a name="how-to-adopt-mta-sts"></a>MTA-STS の導入方法

MTA-STS を使用すると、ドメインで TLS のサポートを宣言し、予想される MX レコードと宛先証明書の通信を行うことができます。 また、問題が発生した場合に送信サーバーが実行する必要があることも示しています。 これは、DNS TXT レコードと HTTPS Web ページとして公開されるポリシー ファイルの組み合わせによって行われます。 HTTPS で保護されたポリシーでは、攻撃者が克服する必要がある別のセキュリティ保護が導入されています。

ドメインの MTA-STS TXT レコードは、送信者によってドメインの HTTPS ベースの MTA-STS ポリシーが取得された後で送信者に対する MTA-STS サポートを示します。 次の TXT レコードは、MTA-STS のサポートを宣言する例です。

`_mta-sts.contoso.com. 3600 IN TXT v=STSv1; id=20220101000000Z;`

ドメインの MTA-STS ポリシーは、ドメインの Web インフラストラクチャによってホストされている事前定義済みの URL に配置される必要があります。 URL 構文は `https://mta-sts.<domain name>/.well-known/mta-sts.txt` です。 たとえば、Microsoft.com のポリシーは <https://mta-sts.microsoft.com/.well-known/mta-sts.txt> で見つかります。

```text
version: STSv1
mode: enforce
mx: *.mail.protection.outlook.com
max_age: 604800
```

MX レコードが直接 Exchange Online を指す顧客は、microsoft.com ポリシーで上に示す値を使用した独自のポリシーで指定できます。 ポリシーで必要な一意の情報は、Exchange Online (`*`.mail.protection.outlook.com) を指す MX レコードであり、同じ証明書がすべての Exchange Online の顧客によって共有されます。 ポリシーを *テスト* モードで公開し、*強制* モードに変更する前にポリシーが有効であることを確認できます。 構成を確認できるサード パーティの検証ツールがあります。

これらのポリシーは、顧客に代わって Exchange Online がホストできるものではなく、顧客は、使用する Web ホスティング サービスを利用する必要があります。 ポリシーは、サブドメイン `mta-sts.<domain name>` の証明書を使用して HTTPS で保護される必要があります。 代わりに、GitHub ページを使用してポリシーをホストする[このソリューション](https://github.com/jpawlowski/mta-sts.template)を含むポリシーをホストする方法もあります。

DNS TXT ドメイン レコードが作成され、必要な HTTPS URL でポリシー ファイルが使用可能になると、ドメインは MTA-STS によって保護されます。MTA-STS の詳細は、[RFC8461](https://datatracker.ietf.org/doc/html/rfc8461) にあります。
