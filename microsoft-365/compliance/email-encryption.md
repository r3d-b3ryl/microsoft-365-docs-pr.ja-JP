---
title: Microsoft 365 でのメールの暗号化
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
ms.assetid: c0d87cbe-6d65-4c03-88ad-5216ea5564e8
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
description: Microsoft Purview Message Encryption、S/MIME、Information Rights Management (IRM) など、Microsoft 365 暗号化のオプションを比較し、トランスポート層セキュリティ (TLS) について紹介します。
ms.openlocfilehash: a5541c9a1478d1eb1add40a5aecb7439d1442e1b
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66624247"
---
# <a name="email-encryption"></a>メールの暗号化

この記事では、Microsoft Purview Message Encryption、S/MIME、Information Rights Management (IRM) など、Microsoft 365 での暗号化のオプションを比較し、トランスポート層セキュリティ (TLS) について紹介します。
  
Microsoft 365 では、電子メールのセキュリティのビジネス ニーズを満たすために複数の暗号化オプションが提供されています。 この記事では、Office 365 でメールを暗号化する 3 つの方法を紹介します。 Office 365 のすべてのセキュリティ機能については、[Office 365 トラスト センター](https://go.microsoft.com/fwlink/p/?LinkID=282470)にアクセスしてください。 この記事では、Microsoft 365 管理者が Office 365 で電子メールを保護する上で役立つ次の 3 つの種類の暗号化を紹介します。
  
- Microsoft Purview Message Encryption。

- Secure/Multipurpose Internet Mail Extensions (S/MIME)。

- Information Rights Management (IRM)。

## <a name="how-microsoft-365-uses-email-encryption"></a>Microsoft 365 のメール暗号化の 使用方法

暗号化とは、認証された受信者だけが特定の情報をデコードおよび利用できるようにその情報をエンコードするプロセスのことです。Microsoft 365 では、サービスでの使用とカスタマー コントロールとしての使用の 2 つの方法で暗号化を使用します。サービスでは、暗号化は Microsoft 365 で既定で使用されるため、ユーザーによる設定は特に必要ありません。たとえば、Microsoft 365 はトランスポート層セキュリティ (TLS) を使用して、2 つのサーバー間の接続またはセッションを暗号化します。 
  
一般的な電子メールの暗号化のしくみは次のとおりです。
  
- メッセージの送信中に送信者のコンピューターまたは中央サーバーによって、メッセージがプレーンテキストから読み取り不可能な暗号テキストに暗号化または変換されます。

- メッセージが途中で読み取られることを防ぐため、送信中のメッセージは暗号テキストのままです。

- 受信者がメッセージを受信すると、メッセージは次の 2 つの方法で読み取り可能なプレーンテキストに変換し直されます。

  - 受信者のコンピューターでキーを使用してメッセージを解読するか、

  - 受信者の身元を確認した後に、受信者の代わりに中央サーバーでメッセージを解読します。

Microsoft 365 内の組織間、または Microsoft 365 と Microsoft 365 外部の信頼できるビジネス パートナー間など、Microsoft 365 でサーバー間の通信をセキュリティで保護する方法については、「[Exchange Online が TLS を使って Office 365 のメール接続をセキュリティで保護する方法](exchange-online-uses-tls-to-secure-email-connections.md)」を参照してください。
    
## <a name="comparing-email-encryption-options-available-in-office-365"></a>Office 365 で使用可能な電子メール暗号化オプションの比較

|メール暗号化技術|![OME を説明する概念アートワーク。](../media/2bf27b5e-bbb3-46d1-95bf-884dc27a746c.png)|![IRM を説明する概念アートワーク](../media/9c0cc444-9448-40c6-b244-8fcc593a64e0.png)|![SMIME を説明する概念アートワーク](../media/ae4613a8-c17e-47e1-8e13-12e891e43744.png)|
|:-----|:-----|:-----|:-----|
|暗号化オプションの説明|Message Encryption は、Azure Rights Management (Azure RMS) で構築され、宛先のメール アドレス (Gmail、Yahoo! Mail、Outlook.com など) に関係なく、暗号化された電子メールを組織内外の宛先に送信できるようにするサービスです。 <br/> 管理者は、暗号化の条件を定義するトランスポート ルールを設定できます。ユーザーがルールに一致するメッセージを送信する場合、自動的に暗号化が適用されます。 <br/> 受信者は、ワンタイム パスコードを取得するか、Microsoft アカウントまたは Office 365 と関連付けられている職場または学校のアカウントを使用してサインインして、暗号化されたメッセージを表示できます。受信者は、暗号化された返信を送信することもできます。暗号化されたメッセージを表示したり、暗号化された返信を送信するのに、受信者は Microsoft 365 サブスクリプションを必要としません。|IRM は、電子メール メッセージに使用制限の適用も行える暗号化ソリューションです。機密情報が権限のないユーザーによって印刷、転送、またはコピーされるのを防止します。 <br/> Microsoft 365 の IRM 機能には Azure Rights Management (Azure RMS) が使用されます。|S/MIME は、メッセージを暗号化およびデジタル署名するための証明書ベースの暗号化ソリューションです。メッセージの暗号化により、指定された受信者だけがメッセージを開き読むことができます。デジタル署名により、受信者は送信者の身元を確認できます。 <br/> デジタル署名と暗号化メッセージのいずれも、独自のデジタル証明書の利用により可能となります。この証明書には、デジタル署名を検証し、メッセージを暗号化し、復号化するための鍵が含まれています。 <br/> S/MIME を使用するには、各受信者のファイルに公開キーが必要です。受信者は独自の秘密キーを管理、保護する必要があります。受信者の秘密キーが危険にさらされた場合、受信者は新しい秘密キーを取得し、すべての潜在的な送信者に公開キーを再配布する必要があります。|
|この機能について|OME: <br/> 内部または外部の受信者に送信されたメッセージを暗号化します。 <br/>  ユーザーは Outlook.com、Yahoo! Mail、および Gmail を含むすべての電子メール アドレスに暗号化されたメッセージを送信できます。 <br/>  管理者であれば、組織のブランドを反映するように電子メール表示ポータルをカスタマイズできます。 <br/> Microsoft がキーを安全に管理および格納するため、ユーザーがそうする必要はありません。 <br/> 暗号化されたメッセージ (HTML 添付ファイルとして送信済み) をブラウザーで開くことができる場合は、クライアント側の特別なソフトウェアは必要ありません。|IRM: <br/> 暗号化と使用制限を利用し、電子メールのメッセージと添付ファイルをオンラインとオフラインで保護します。 <br/> 管理者には、自動的に IRM を適用してメッセージを選択するためのトランスポート ルールまたは Outlook 保護ルールを設定する権限が付与されます。 <br/> ユーザーは Outlook または Outlook on the web (旧称: Outlook Web App) で手動でテンプレートを適用できます。|S/MIME は、デジタル署名による送信者の認証および暗号化によるメッセージの機密性を処理します。|
|暗号化オプションの限界|OME では、メッセージに利用制限を適用できません。たとえば、受信者が暗号化メッセージを転送したり印刷したりするのを制限することはできません。|アプリケーションによっては、一部のデバイスで IRM メールを利用できないことがあります。以上の製品と IRM メールに対応しているその他の製品に関する詳細については、「[クライアント デバイスの機能](/azure/information-protection/requirements#BKMK_ClientCapabilities)」を参照してください。|S/MIME では、マルウェア、スパム、およびポリシーについて、暗号化されたメッセージをスキャンできません。|
|推奨事項とシナリオ例|顧客でも、他の会社でも、組織外のユーザーに機密のビジネス情報を送信する場合は、OME を使用することをお勧めします。例:  <br/>  顧客にクレジット カード請求書を送信する銀行員  <br/>  患者に医療記録を送信する診療所  <br/>  他の弁護士に法的な機密情報を送信する弁護士|使用制限と暗号化の両方を適用する場合は、IRM を使用することをお勧めします。例:  <br/>  新しい製品に関する機密情報の詳細をチームに送信するマネージャーが [転送不可] オプションを適用する場合。  <br/>  エグゼクティブが、Office 365 を使用しているパートナーからの添付ファイルを含む重要な提案書を別の会社と共有しなければならず、電子メールと添付ファイルの両方を保護する必要がある場合。|ユーザーの組織または受信者の組織のいずれかが、適切なピアツーピア暗号化を必要とする場合は、S/MIME を使用することをお勧めします。  <br/>  S/MIME は、次のシナリオで最もよく使用されます。  <br/>  他の政府機関と通信する政府機関  <br/>  政府機関と通信する会社|
||

## <a name="what-encryption-options-are-available-for-my-microsoft-365-subscription"></a>使用中の Microsoft 365 サブスクリプションでは、どの暗号化オプションを利用できますか?

Microsoft 365 サブスクリプションの電子メール暗号化オプションについては、「[Exchange Online サービスの説明](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)」を参照してください。そこには次の暗号化機能に関する情報があります。
  
- IRM 機能と Microsoft Purview Message Encryption の両方を含む Azure RMS

- S/MIME

- TLS

- 保存中のデータの暗号化 (BitLocker を使用)

Microsoft 365 で、PGP (Pretty Good Privacy) などのサードパーティ製の暗号化ツールを使用することもできます。 Microsoft 365 は PGP/MIME をサポートしていません。PGP で暗号化されたメールを送受信する場合にのみ PGP/インラインを使用できます。

## <a name="what-about-encryption-for-data-at-rest"></a>保存中のデータの暗号化について

"Data at rest (格納中のデータ)" とは、頻繁に送信されないデータを意味します。Microsoft 365 では、格納中の電子メール データは BitLocker ドライブ暗号化で暗号化されます。BitLocker は Microsoft 365 データセンターのハード ドライブを暗号化し、無許可のアクセスに対する保護機能を強化します。詳細については、「[BitLocker 概要](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831713(v=ws.11))」を参照してください。
  
## <a name="more-information-about-email-encryption-options"></a>電子メール暗号化オプションの詳細

この記事の電子メール暗号化オプションと TLS の詳細については、次の記事を参照してください。
  
**Microsoft Purview のメッセージの暗号化**
  
[メッセージの暗号化](ome.md)
  
**IRM**
  
[Exchange Online での Information Rights Management](./information-rights-management-in-exchange-online.md)
  
[Azure Active Directory Rights Management の概要](/azure/information-protection/what-is-azure-rms)
  
**S/MIME**
  
[S/MIME によるメッセージの署名と暗号化](/Exchange/policy-and-compliance/smime/smime)
  
[S/MIME について](/previous-versions/tn-archive/aa995740(v=exchg.65))
  
[公開キー暗号について](/previous-versions/tn-archive/aa998077(v=exchg.65))
  
**TLS**
  
[コネクタを使用してカスタム メール フローを構成する](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
