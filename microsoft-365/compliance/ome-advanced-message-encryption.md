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
ms.localizationpriority: medium
ms.date: 05/12/2022
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 高度なメッセージ暗号化は、管理者が保護されたメッセージでさらに多くのことを行うことを可能にすることで、組織がコンプライアンスの義務を果たすのに役立ちます。
ms.openlocfilehash: a4b970c005b49067e59254ff549200a9118f6cd4
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66632159"
---
# <a name="advanced-message-encryption"></a>高度なメッセージ暗号化

Microsoft Purview Advanced Message Encryption は[、Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 E5、Microsoft 365 E5 (非営利団体スタッフ価格)、Office 365 Enterprise E5 (非営利団体スタッフ価格)、およびOffice 365 Education A5。 組織に Microsoft Purview Advanced Message Encryption を含まないサブスクリプションがある場合は、Microsoft 365 E3、Microsoft 365 E3 (非営利団体スタッフ価格)、またはMicrosoft 365 E5 Compliance SKU アドオンで購入できます。Microsoft 365 E3、Microsoft 365 E3 (非営利団体スタッフの価格)、Office 365 SKU、またはMicrosoft 365 E5/A5 Information Protection用のOffice 365 Advanced Compliance SKU アドオン Microsoft 365 A3/E3 用のガバナンス SKU アドオン。

高度なメッセージ暗号化は、外部受信者と暗号化された電子メールへのアクセスに対してより柔軟な制御を必要とするコンプライアンスの義務を満たすのに役立ちます。 Office 365の高度なメッセージ暗号化を使用すると、自動ポリシーを使用して組織外で共有される機密メールを制御し、暗号化されたメッセージ ポータルのアクセス ログを使用してそれらのアクティビティを追跡できます。 PII、財務、正常性 ID などの機密情報の種類を識別するようにこれらのポリシーを構成するか、キーワードを使用して保護を強化することができます。 ポリシーを構成したら、ポリシーとカスタム ブランドの電子メール テンプレートを組み合わせ、ポリシーに合った電子メールをさらに制御するための有効期限を追加します。 また、管理者は、いつでもメールへのアクセスを取り消すことで、セキュリティで保護された Web ポータルを介して外部からアクセスされる暗号化されたメールをさらに制御できます。

外部の受信者に送信された電子メールの有効期限を取り消して設定することだけが可能です。

## <a name="get-started-with-microsoft-purview-advanced-message-encryption"></a>Microsoft Purview Advanced Message Encryption の使用を開始する

次の記事では、高度なメッセージ暗号化を設定して使用する方法について説明します。

組織には、Microsoft Purview Advanced Message Encryption を含むサブスクリプションが必要です。 サポートされているサブスクリプションの詳細については、 [メッセージ ポリシーとコンプライアンス サービスの説明](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)を参照してください。

Office 365メッセージ暗号化がまだ設定されていない場合は、「[新しいOffice 365メッセージ暗号化機能を設定する](set-up-new-message-encryption-capabilities.md)」を参照してください。

高度なメッセージ暗号化では、1 つのブランド 化テンプレートに限定されません。 代わりに、複数のブランド化テンプレートを作成して使用できます。 カスタム ブランドを追加すると、暗号化されたメッセージの失効を追跡することもできます。 詳細については、「 [暗号化されたメッセージに組織のブランドを追加する」を参照してください](add-your-organization-brand-to-encrypted-messages.md)。 カスタム ブランドを使用すると、外部の受信者は、OME ポータルへのリンクを含む通知メールを受け取ります。 メール フロー ルールは、通知メールと OME ポータルで使用するブランド テンプレートを決定します。 これにより、セキュリティで保護されたコンテンツは組織の外部に送信されません。

メッセージを取り消し、有効期限をユーザーがポータルから受け取るメッセージにのみ適用できます。 つまり、カスタム ブランド テンプレートが適用された電子メール。 詳細と例については、「 [すべての外部受信者が OME ポータルを使用して暗号化されたメールを読み取っていることを確認する](manage-office-365-message-encryption.md#ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail)」のガイダンスを参照してください。

[Microsoft Purview Advanced Message Encryption によって暗号化された電子メールの有効期限を設定](ome-advanced-expiration.md)します。 セキュリティで保護された Web ポータルから暗号化された電子メールへのアクセスを期限切れにすることで保護を強化する自動ポリシーを使用して、組織外で共有される機密性の高いメールを制御します。

[Microsoft Purview Advanced Message Encryption によって暗号化された電子メールを取り消します](revoke-ome-encrypted-mail.md)。 組織外で共有される機密性の高いメールを制御し、セキュリティで保護された Web ポータルから暗号化された電子メールへのアクセスを取り消すことで保護を強化します。

[Microsoft Purview Advanced Message Encryption による暗号化されたメッセージ ポータル アクティビティ ログ](ome-message-access-logs.md)。 暗号化されたメッセージ ポータルで、組織外で共有されている機密性の高いメールを監視します。
