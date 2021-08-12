---
title: 高度なメッセージ暗号化
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 10/16/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 高度なメッセージ暗号化は、管理者が保護されたメッセージを使用してさらに多くのことを行うのを有効にすることで、組織がコンプライアンスの義務を果たすのに役立ちます。
ms.openlocfilehash: d1021d4d424a1ecb984bfd5afa176e9ae3a3451c006df0dd307a5b59d9e4d0e7
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53813657"
---
# <a name="advanced-message-encryption"></a>高度なメッセージ暗号化

Office 365 Advanced Message Encryptionは[、Microsoft 365 Enterprise E5、Office 365 E5、Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise/home)(非営利スタッフ価格)、Office 365 Enterprise E5 (非営利スタッフ価格)、および Office 365 Education A5 に含まれています。 組織に Office 365 Advanced Message Encryption を含めないサブスクリプションがある場合は、Microsoft 365 E3、Microsoft 365 E3 Office 365 Advanced Compliance (非営利スタッフ価格) の Microsoft 365 E5 Compliance SKU アドオン、Microsoft 365 E3、Microsoft 365 E3 (非営利スタッフ価格)、Office 365 SKU、Microsoft 365 E5/A5 Information Protection and Governance SKU アドオンを使用して購入できます。Microsoft 365 A3/E3 用。

高度なメッセージ暗号化は、お客様が外部の受信者と暗号化された電子メールへのアクセスに対してより柔軟な制御を必要とするコンプライアンスの義務を満たすのに役立ちます。 [高度なメッセージの暗号化] Office 365、組織外で共有される機密性の高いメールを自動ポリシーで制御できます。 これらのポリシーを構成して、PII、Financial、Health などの機密情報の種類を識別するか、キーワードを使用して保護を強化できます。 ポリシーを構成したら、ポリシーをカスタム ブランドの電子メール テンプレートと組み合わせ、ポリシーに合った電子メールを特別に制御する有効期限を追加します。 また、管理者は、いつでもメールへのアクセスを取りやめて、セキュリティで保護された Web ポータルを介して外部からアクセスされる暗号化されたメールをさらに制御できます。

外部受信者に送信される電子メールの有効期限のみを取り消して設定できます。

## <a name="get-started-with-office-365-advanced-message-encryption"></a>ユーザーの使用を開始Office 365 Advanced Message Encryption

次の記事では、高度なメッセージ暗号化を設定して使用する方法について説明します。

組織には、サブスクリプションが含まれる必要Office 365 Advanced Message Encryption。 サポートされているサブスクリプションの詳細については、「メッセージ ポリシーとコンプライアンス サービスの [説明」を参照してください](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)。

既にセットアップされていない場合Office 365 Message Encryption、新しい機能をセットアップする[Office 365 Message Encryption参照してください](set-up-new-message-encryption-capabilities.md)。

高度なメッセージ暗号化を使用すると、1 つのブランド テンプレートに限定されません。 代わりに、複数のブランド テンプレートを作成して使用できます。 詳細については、「 [暗号化されたメッセージに組織のブランドを追加する」を参照してください](add-your-organization-brand-to-encrypted-messages.md)。

[ユーザーが暗号化した電子メールの有効期限をOffice 365 Advanced Message Encryption。](ome-advanced-expiration.md) セキュリティで保護された Web ポータルから暗号化された電子メールへのアクセスを期限切れにすることで保護を強化する自動ポリシーを使用して、組織外で共有される機密性の高いメールを制御します。

[ユーザーが暗号化した電子メールをOffice 365 Advanced Message Encryption](revoke-ome-encrypted-mail.md)します。 セキュリティで保護された Web ポータルから暗号化されたメールへのアクセスを取りやめ、組織外で共有される機密性の高いメールを制御し、保護を強化します。  

カスタム Office 365 Advanced Message Encryptionを適用すると、Microsoft はテンプレートを適用するメール フロー ルールに適合するラッパーを電子メールに適用します。 メッセージを取り消し、ユーザーがポータルを通じて受信するメッセージにのみ有効期限を適用できます。 つまり、カスタム ブランド テンプレートが適用されている電子メール。 詳細と例については、「すべての外部受信者が OME ポータルを使用して暗号化されたメールを読み取る」の [ガイダンスを参照してください](manage-office-365-message-encryption.md#ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail)。