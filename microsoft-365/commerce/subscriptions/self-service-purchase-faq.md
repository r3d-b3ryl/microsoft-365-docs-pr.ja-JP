---
title: セルフサービス購入についてよく寄せられる質問
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom:
- AdminSurgePortfolio
- aka.ms/self-service-purchase-faq
search.appverid:
- MET150
description: セルフサービス購入に関してよく寄せられる質問に対する回答を確認できます。
ms.date: 08/12/2020
ms.openlocfilehash: 78a7082a966a866f18ac2aa378198dbb33d8c158
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653703"
---
# <a name="self-service-purchase-faq"></a>セルフサービス購入についてよく寄せられる質問

セルフサービス購入により、ユーザーは新しいテクノロジを試して、より大規模な組織を最終的に利益するソリューションを開発する機会を得ることができます。 中央の調達と IT teams は、 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>を介してセルフサービス購入ソリューションを購入して展開するすべてのユーザーに対して表示されます。 管理者は、PowerShell を使用して製品ごとにセルフサービス購入を無効にすることができます。 詳細については、「 [Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)」を参照してください。

セルフサービス購入は、電源プラットフォーム (Power BI、電源アプリ、および電源自動化)、プロジェクト、Visio で利用できます。

> [!NOTE]
> セルフサービス購入はインドでは利用できず、政府または教育機関のお客様は利用できません。

## <a name="making-a-self-service-purchase"></a>セルフサービス購入の作成

### <a name="how-does-a-customer-make-a-self-service-purchase"></a>お客様はどのようにしてセルフサービス購入を行いますか?

お客様は、製品の web サイトから、またはアプリ内購入プロンプトからセルフサービス購入を行うことができます。 お客様は、既存の Azure Active Directory (AD) テナント内のユーザーであることを確認するために、最初にメールアドレスを入力するよう求められています。 次に、Azure AD 資格情報を使用してサインインするように指示されています。 サインインした後、お客様は購入するサブスクリプションの数を選択し、クレジットカードの支払いを指定するように求められます。 購入が完了すると、サブスクリプションの使用を開始できるようになります。 買い手は、組織内の他のユーザーにライセンスを製品に割り当てることができる、 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a> の制限されたビューにアクセスできます。

### <a name="what-are-the-payment-options-for-self-service-purchases"></a>セルフサービス購入の支払いオプションとは

現時点では、クレジットカードのみが利用可能な支払い方法です。 請求による支払いはサポートされていません。

### <a name="who-can-buy-through-self-service-purchase"></a>セルフサービス購入で購入できるユーザー

管理された Azure AD テナントのゲスト以外のユーザーアカウントを持つユーザーは、セルフサービス購入を行うことができます。 セルフサービス購入は、官公庁または教育機関のテナントでは使用できません。 これが組織に当てはまる場合は、セルフサービス購入を制御するために追加の操作は必要ありません。

セルフサービス購入の対象になっていない組織または市場のユーザーには、IT 管理者に連絡するように求めるメッセージが表示されます。

### <a name="can-guest-users-buy-through-self-service-purchase"></a>ゲストユーザーはセルフサービス購入で購入できますか?

いいえ、ゲストユーザーはゲストになっているテナントでセルフサービス購入を完了できません。

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a>オンプレミスの Active Directory からのユーザーの同期は、セルフサービスの購入で行うことができますか。

ユーザーが適格な Azure AD テナントにアクティブなユーザーアカウントを持っている場合は、セルフサービス購入を完了できます。

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a>セルフサービスの purchasers にライセンスを割り当てることができるユーザー

セルフサービス purchasers では、同じ Azure AD テナント内のユーザーにのみライセンスを割り当てることができます。 購入者は、ライセンスを割り当てるために <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a> の限定されたビューにアクセスできます。 Purchasers は、セルフサービス購入で購入した製品にライセンスを割り当てることができ、同じ Azure AD テナント内のユーザーに対してのみライセンスを割り当てることができます。

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a>セルフサービスの購入者は購入を確認して管理しますか?

セルフサービス purchasers では、 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>の限定されたビューで購入を管理できます。 Purchasers は、常に、Microsoft 365 および Dynamics online のすべてのアプリに組み込まれているアプリ起動ツールの **管理者** タイルから管理センターにアクセスできます。 Purchasers では、作成した購入を表示したり、同じサービスに対して追加のサブスクリプションを購入したり、それらのサブスクリプションのライセンスを組織内の他のユーザーに割り当てることができます。 また、purchasers は、請求書の表示と支払い、支払い方法の更新、およびサブスクリプションのキャンセルを行うことができます。

## <a name="pricing"></a>価格設定

### <a name="what-is-the-pricing-for-self-service-purchases"></a>セルフサービス購入の価格設定について

セルフサービス購入の各製品の価格は、Microsoft の web サイトでご利用いただけます。 また、ユーザーがセルフサービス購入を行うときに、支払いの処理の一部として価格も表示されます。 これらの価格は、パートナーによって集中購入または料金を提示する際に組織が支払う価格とは異なる場合があります。

### <a name="who-is-responsible-for-payment"></a>支払いの責任者

セルフサービス購入によってサブスクリプションを購入するユーザーとは、請求先の人物、および購入の諸条件と価格に基づいて支払いの責任者をいいます。

## <a name="admin-capabilities"></a>管理機能

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a>セルフサービス購入における管理者の権限を教えてください

管理者は、組織内で行われたすべてのセルフサービスの購入を <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>で確認できます。 これらのユーザーは、製品、購入者名、購入したサブスクリプション、有効期限、注文履歴、購入価格、および割り当てられたユーザーを各セルフサービス購入に対して確認できます。 電源プラットフォーム管理センターでは、管理者はセルフサービス購入容量を表示することもできます。 組織に必要な場合、管理者は、PowerShell を使用して製品ごとにセルフサービス購入を無効にすることができます。 管理者は、セルフサービス購入された製品と一元的に購入された製品に対して、同じデータ管理およびアクセスポリシーを有します。

管理者は、組織内のユーザーがセルフサービス購入を行うことができるかどうかを制御することもできます。 詳細については、「 [Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)」を参照してください。

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a>セルフサービス購入を有効にすることによって、Microsoft はデータガバナンスとコンプライアンスをどのように重視していますか?

管理者は、データガバナンスとコンプライアンスの要件に基づいて、テナント内で使用可能なサービスと製品を制御します。 組織で有効になっているすべてのデータ管理およびアクセスポリシーは、利用可能なセルフサービス購入サービスに適用されます。

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a>セルフサービス購入から作成された製品データの所有者

セルフサービス購入で購入した製品から作成されたデータは、組織によって所有および制御されます。

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a>セルフサービス購入で行われた購入を一元管理するにはどうすればよいですか?

管理者は既存のライセンスを割り当てることも、セルフサービス購入製品の追加サブスクリプションを購入することもできます。これには、既存の契約と、セルフサービス購入に割り当てられたユーザーの料金があります。 これらの集中的に購入したライセンスを割り当てた後、管理者は purchasers に既存のサブスクリプションをキャンセルするよう要求できます。

### <a name="where-does-the-admin-see-self-service-purchases"></a>管理者はどこにセルフサービス購入を表示しますか?

グローバルおよび課金管理者は、 **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>で**製品**を請求する際に、セルフサービス購入により購入したサブスクリプションを確認できます。 [製品] リストにフィルターを適用して、中央の調達で購入されたサブスクリプションのみを表示したり、セルフサービス購入で購入したサブスクリプションを含めることができます。

管理者は、製品、買い手名、購入したサブスクリプション、有効期限、注文履歴、購入価格、割り当てられたユーザーを表示できます。

## <a name="support-and-training"></a>サポートとトレーニング

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a>お客様の IT 部門やパートナーは、セルフサービス購入によって購入された製品をサポートすることを期待していますか。

IT 部門およびパートナーは、セルフサービス購入を通じて購入された製品に対するサポートを提供することを期待していません。 Microsoft は、セルフサービスの purchasers の標準サポートを提供しています。

### <a name="if-a-self-service-purchaser-calls-support-does-that-use-the-customers-premier-support-incidents"></a>セルフサービスの購入者がサポートに電話をかける場合、お客様のプレミアサポートインシデントを使用していますか?

セルフサービス purchasers では、お客様のプレミアサポートインシデントを使用してセルフサービス購入のサポートを受けることはできません。

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a>セルフサービス購入で購入した製品について、ユーザーはどのようにトレーニングを受けられるようになりますか?

ユーザー向けの豊富なトレーニングは、製品 web サイトで提供されています。 これらの製品には、他のユーザーから直接回答やヒントを得るためのガイド学習、ドキュメント、サンプル、および強力なコミュニティが用意されています。

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a>ユーザーが組織を離れた場合、セルフサービス購入はどうなりますか?

最初にセルフサービス購入製品を購入したユーザーが組織を離れた場合、有効なユーザーは、サブスクリプションの期間中は製品を引き続き完全に使用できます。 サブスクリプションは、購入者が直接取り消すか、カスタマーサポートによってサブスクリプションのキャンセルを要求するまでアクティブなままになります。 管理者は、解約されたサブスクリプションのユーザーに対して、集中購入したライセンスを割り当てることもできます。

## <a name="partners"></a>パートナー

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a>セルフサービス購入における Microsoft のパートナーの役割

管理権限を委任されたパートナーは、管理者と同様に、 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>でセルフサービス購入を表示できます。パートナーは、セルフサービス購入によって購入された製品を集中管理する組織のサポートに役立ちます。 また、パートナーは、セルフサービス購入の機能を拡張するためのソリューションを提供することができます。