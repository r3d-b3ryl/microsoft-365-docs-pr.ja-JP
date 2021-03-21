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
ms.openlocfilehash: 8c650c47c1853102e4e2d142040e49724ef707e0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923957"
---
# <a name="advanced-message-encryption"></a>高度なメッセージ暗号化

Office 365 Advanced Message Encryption は [、Microsoft 365 Enterprise E5、Office](https://www.microsoft.com/microsoft-365/enterprise/home)365 E5、Microsoft 365 E5 (非営利スタッフ価格)、Office 365 Enterprise E5 (非営利スタッフ価格)、および Office 365 Education A5 に含まれています。 組織に Office 365 Advanced Message Encryption を含めないサブスクリプションがある場合は、Microsoft 365 E3 の Microsoft 365 E5 コンプライアンス SKU アドオンで購入できます。 Microsoft 365 E3 (非営利スタッフ価格)、または Microsoft 365 E3、Microsoft 365 E3 (非営利スタッフ価格)、Office 365 SKU、または Microsoft 365 E5/A5 情報保護およびガバナンス SKU アドオン用の Office 365 Advanced Compliance SKU アドオン。

高度なメッセージ暗号化は、お客様が外部の受信者と暗号化された電子メールへのアクセスに対してより柔軟な制御を必要とするコンプライアンスの義務を満たすのに役立ちます。 365 の高度なメッセージ暗号化Office、組織外で共有される機密性の高い電子メールを自動ポリシーで制御できます。 これらのポリシーを構成して、PII、Financial、Health などの機密情報の種類を識別するか、キーワードを使用して保護を強化できます。 ポリシーを構成したら、ポリシーをカスタム ブランドの電子メール テンプレートと組み合わせ、ポリシーに合った電子メールを特別に制御する有効期限を追加します。 また、管理者は、いつでもメールへのアクセスを取りやめて、セキュリティで保護された Web ポータルを介して外部からアクセスされる暗号化されたメールをさらに制御できます。

外部受信者に送信される電子メールの有効期限のみを取り消して設定できます。

## <a name="get-started-with-office-365-advanced-message-encryption"></a>365 Advanced message Encryption Officeの使用を開始する

次の記事では、高度なメッセージ暗号化を設定して使用する方法について説明します。

組織には、365 Advanced Message Encryption Officeサブスクリプションが必要です。 サポートされているサブスクリプションの詳細については、「メッセージ ポリシーとコンプライアンス サービスの [説明」を参照してください](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)。

365 Message Encryption をOfficeしていない場合は [、「365](set-up-new-message-encryption-capabilities.md)Message Encryption の新しい機能Officeセットアップする」を参照してください。

高度なメッセージ暗号化を使用すると、1 つのブランド テンプレートに限定されません。 代わりに、複数のブランド テンプレートを作成して使用できます。 詳細については、「 [暗号化されたメッセージに組織のブランドを追加する」を参照してください](add-your-organization-brand-to-encrypted-messages.md)。

[365](ome-advanced-expiration.md)Advanced Message Encryption Officeメールの有効期限を設定します。 セキュリティで保護された Web ポータルから暗号化された電子メールへのアクセスを期限切れにすることで保護を強化する自動ポリシーを使用して、組織外で共有される機密性の高いメールを制御します。

[365 Advanced Message Encryption Office暗号化された電子メールを取り消します](revoke-ome-encrypted-mail.md)。 セキュリティで保護された Web ポータルから暗号化されたメールへのアクセスを取りやめ、組織外で共有される機密性の高いメールを制御し、保護を強化します。  

365 Office高度なメッセージ暗号化を使用すると、カスタム ブランド テンプレートを適用する場合はいつでも、テンプレートを適用するメール フロー ルールに適合するラッパーがメールに適用されます。 メッセージを取り消し、ユーザーがポータルを通じて受信するメッセージにのみ有効期限を適用できます。 つまり、カスタム ブランド テンプレートが適用されている電子メール。 詳細と例については、「すべての外部受信者が OME ポータルを使用して暗号化されたメールを読み取る」の [ガイダンスを参照してください](manage-office-365-message-encryption.md#ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail)。