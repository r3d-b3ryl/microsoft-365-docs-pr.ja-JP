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
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: c0d87cbe-6d65-4c03-88ad-5216ea5564e8
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
description: Office Message Encryption (OME)、S/MIME、Information Rights Management (IRM) など、Microsoft 365 暗号化のオプションを比較し、トランスポート層セキュリティ (TLS) について紹介します。
ms.openlocfilehash: 81ce8ca567c2b696060a1dd41b9af06bfc7b94a7
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769055"
---
# <a name="email-encryption"></a>メールの暗号化

この記事では、Office Message Encryption (OME)、S/MIME、Information Rights Management (IRM) など、Microsoft 365 での暗号化のオプションを比較し、トランスポート層セキュリティ (TLS) について紹介します。
  
Microsoft 365 delivers multiple encryption options to help you meet your business needs for email security. This article presents three ways to encrypt email in Office 365. If you want to learn more about all security features in Office 365, visit the [Office 365 Trust Center](https://go.microsoft.com/fwlink/p/?LinkID=282470). This article introduces the three types of encryption available for Microsoft 365 administrators to help secure email in Office 365:
  
- Office Message Encryption (OME)。

- Secure/Multipurpose Internet Mail Extensions (S/MIME)。

- Information Rights Management (IRM)。

## <a name="email-encryption-and-how-microsoft-365-uses-it"></a>メールの暗号化と Microsoft 365 の使用方法

Encryption is the process by which information is encoded so that only an authorized recipient can decode and consume the information. Microsoft 365 uses encryption in two ways: in the service, and as a customer control. In the service, encryption is used in Microsoft 365 by default; you don't have to configure anything. For example, Microsoft 365 uses Transport Layer Security (TLS) to encrypt the connection, or session, between two servers. 
  
一般的な電子メールの暗号化のしくみは次のとおりです。
  
- メッセージの送信中に送信者のコンピューターまたは中央サーバーによって、メッセージがプレーンテキストから読み取り不可能な暗号テキストに暗号化または変換されます。

- メッセージが途中で読み取られることを防ぐため、送信中のメッセージは暗号テキストのままです。

- 受信者がメッセージを受信すると、メッセージは次の 2 つの方法で読み取り可能なプレーンテキストに変換し直されます。

  - 受信者のコンピューターでキーを使用してメッセージを解読するか、

  - 受信者の身元を確認した後に、受信者の代わりに中央サーバーでメッセージを解読します。

Microsoft 365 内の組織間、または Microsoft 365 と Microsoft 365 外部の信頼できるビジネス パートナー間など、Microsoft 365 でサーバー間の通信をセキュリティで保護する方法については、「[Exchange Online が TLS を使って Office 365 のメール接続をセキュリティで保護する方法](exchange-online-uses-tls-to-secure-email-connections.md)」を参照してください。
  
[Office 365 の暗号化](https://www.youtube.com/watch?v=KmfxCd5ublI)の概要はこの動画でご覧いただけます。
  
## <a name="comparing-email-encryption-options-available-in-office-365"></a>Office 365 で使用可能な電子メール暗号化オプションの比較

||![OME を説明する概念アートワーク](../media/2bf27b5e-bbb3-46d1-95bf-884dc27a746c.png)|![IRM を説明する概念アートワーク](../media/9c0cc444-9448-40c6-b244-8fcc593a64e0.png)|![SMIME を説明する概念アートワーク](../media/ae4613a8-c17e-47e1-8e13-12e891e43744.png)|
|:-----|:-----|:-----|:-----|
|暗号化オプションの説明|Office 365 Message Encryption (OME) は、Azure Rights Management (Azure RMS) で構築され、宛先のメール アドレス (Gmail、Yahoo! Mail、Outlook.com など) に関係なく、暗号化された電子メールを組織内外の宛先に送信できるようにするサービスです。 <br/> 管理者は、暗号化の条件を定義するトランスポート ルールを設定できます。ユーザーがルールに一致するメッセージを送信する場合、自動的に暗号化が適用されます。 <br/> To view encrypted messages, recipients can either get a one-time passcode, sign in with a Microsoft account, or sign in with a work or school account associated with Office 365. Recipients can also send encrypted replies. They don't need a Microsoft 365 subscription to view encrypted messages or send encrypted replies.|IRM は、電子メール メッセージに使用制限の適用も行える暗号化ソリューションです。機密情報が権限のないユーザーによって印刷、転送、またはコピーされるのを防止します。 <br/> Microsoft 365 の IRM 機能には Azure Rights Management (Azure RMS) が使用されます。|S/MIME is a certificate-based encryption solution that allows you to both encrypt and digitally sign a message. The message encryption helps ensure that only the intended recipient can open and read the message. A digital signature helps the recipient validate the identity of the sender. <br/> デジタル署名と暗号化メッセージのいずれも、独自のデジタル証明書の利用により可能となります。この証明書には、デジタル署名を検証し、メッセージを暗号化し、復号化するための鍵が含まれています。 <br/> To use S/MIME, you must have public keys on file for each recipient. Recipients have to maintain their own private keys, which must remain secure. If a recipient's private keys are compromised, the recipient needs to get a new private key and redistribute public keys to all potential senders.|
|この機能について|OME: <br/> 内部または外部の受信者に送信されたメッセージを暗号化します。 <br/>  ユーザーは Outlook.com、Yahoo! Mail、および Gmail を含むすべての電子メール アドレスに暗号化されたメッセージを送信できます。 <br/>  管理者であれば、組織のブランドを反映するように電子メール表示ポータルをカスタマイズできます。 <br/> Microsoft がキーを安全に管理および格納するため、ユーザーがそうする必要はありません。 <br/> 暗号化されたメッセージ (HTML 添付ファイルとして送信済み) をブラウザーで開くことができる場合は、クライアント側の特別なソフトウェアは必要ありません。|IRM: <br/> 暗号化と使用制限を利用し、電子メールのメッセージと添付ファイルをオンラインとオフラインで保護します。 <br/> 管理者には、自動的に IRM を適用してメッセージを選択するためのトランスポート ルールまたは Outlook 保護ルールを設定する権限が付与されます。 <br/> ユーザーは Outlook または Outlook on the web (旧称: Outlook Web App) で手動でテンプレートを適用できます。|S/MIME は、デジタル署名による送信者の認証および暗号化によるメッセージの機密性を処理します。|
|暗号化オプションの限界|OME doesn't let you apply usage restrictions to messages. For example, you can't use it to stop a recipient from forwarding or printing an encrypted message.|Some applications may not support IRM emails on all devices. For more information about these and other products that support IRM email, see [Client device capabilities](https://technet.microsoft.com/library/dn655136.aspx#BKMK_ClientCapabilities).|S/MIME では、マルウェア、スパム、およびポリシーについて、暗号化されたメッセージをスキャンできません。|
|推奨事項とシナリオ例|We recommend using OME when you want to send sensitive business information to people outside your organization, whether they're consumers or other businesses. For example:  <br/>  顧客にクレジット カード請求書を送信する銀行員  <br/>  患者に医療記録を送信する診療所  <br/>  他の弁護士に法的な機密情報を送信する弁護士|使用制限と暗号化の両方を適用する場合は、IRM を使用することをお勧めします。例:  <br/>  新しい製品に関する機密情報の詳細をチームに送信するマネージャーが [転送不可] オプションを適用する場合。  <br/>  エグゼクティブが、Office 365 を使用しているパートナーからの添付ファイルを含む重要な提案書を別の会社と共有しなければならず、電子メールと添付ファイルの両方を保護する必要がある場合。|ユーザーの組織または受信者の組織のいずれかが、適切なピアツーピア暗号化を必要とする場合は、S/MIME を使用することをお勧めします。  <br/>  S/MIME は、次のシナリオで最もよく使用されます。  <br/>  他の政府機関と通信する政府機関  <br/>  政府機関と通信する会社|
||

[Azure Information Protection](https://docs.microsoft.com/microsoft-365/compliance/protect-information) とメール暗号化の両方を使用してデータを保護する場合は、次のことを検討してください。
- OME および IRM 暗号化で秘密度ラベルを使用できます。 詳細については、「[秘密度ラベルを使用して暗号化を適用してコンテンツへのアクセスを制限する](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels?view=o365-worldwide#what-happens-to-existing-encryption-when-a-labels-applied)」を参照してください。
- S/MIME を使用してデジタル署名されたメールに秘密度ラベルを適用できます。
- エンドツーエンド暗号化によって保護されたメッセージはポリシーによって処理されないため、S/MIME を使用して暗号化されたメールに秘密度ラベルを適用することはできません。

## <a name="encryption-options-available-for-my-microsoft-365-subscription"></a>Microsoft 365 サブスクリプションで利用可能な暗号化オプション

Microsoft 365 サブスクリプションの電子メール暗号化オプションについては、「[Exchange Online サービスの説明](https://technet.microsoft.com/library/exchange-online-service-description.aspx)」を参照してください。 ここでは、次の暗号化の機能に関する情報を確認できます。

- IRM 機能と新しい OME 機能の両方を含む Azure RMS

- S/MIME

- TLS

- 保存中のデータの暗号化 (BitLocker を使用)

Microsoft 365 で、PGP (Pretty Good Privacy) などのサードパーティ製の暗号化ツールを使用することもできます。 Microsoft 365 は PGP/MIME をサポートしていません。PGP で暗号化されたメールを送受信する場合にのみ PGP/インラインを使用できます。

## <a name="what-about-encryption-for-data-at-rest"></a>保存中のデータの暗号化について

"保存データ" とは、アクティブに送信されている過程にはないデータです。 Microsoft 365 では、保存中の電子メール データは BitLocker ドライブ暗号化を使用して暗号化されます。 BitLocker は、Microsoft 365 データセンター内のハード ドライブを暗号化し、権限のないアクセスに対する保護を強化します。 詳細については、「[BitLocker の概要](https://go.microsoft.com/fwlink/p/?LinkId=394737)」を参照してください。
  
## <a name="more-information-about-email-encryption-options"></a>電子メール暗号化オプションの詳細

この記事の電子メール暗号化オプションと TLS の詳細については、次の記事を参照してください。
  
**OME**
  
[Office 365 Message Encryption (OME)](ome.md)
  
**IRM**
  
[Exchange Online での Information Rights Management](https://technet.microsoft.com/library/jj983436%28v=exchg.150%29.aspx)
  
[Azure Active Directory Rights Management の概要](https://technet.microsoft.com/library/jj585026)
  
**S/MIME**
  
[S/MIME によるメッセージの署名と暗号化](https://technet.microsoft.com/library/dn626158)
  
[S/MIME について](https://technet.microsoft.com/library/aa995740%28v=exchg.65%29.aspx)
  
[公開キー暗号について](https://technet.microsoft.com/library/aa998077%28v=exchg.65%29.aspx)
  
**TLS**
  
[コネクタを使用してカスタム メール フローを構成する](https://technet.microsoft.com/library/jj723138%28v=exchg.150%29.aspx)
