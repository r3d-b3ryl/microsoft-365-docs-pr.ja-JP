---
title: セルフサービス購入についてよく寄せられる質問
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
search.appverid:
- MET150
description: セルフサービス購入に関してよく寄せられる質問に対する回答を確認できます。
ms.custom: aka.ms/self-service-purchase-faq
ms.openlocfilehash: a9e49f5b9b518711f72c9b9a29e690c55acf3861
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42080311"
---
# <a name="self-service-purchase-faq"></a>セルフサービス購入についてよく寄せられる質問

> [!NOTE]
> この記事に記載されている情報は、Microsoft 電源プラットフォーム (Power BI、電源アプリ、およびパワー自動化) サブスクリプションにのみ適用されます。

米国、オーストラリア、カナダ、および日本の電源プラットフォームでセルフサービス購入が可能になりました。

## <a name="general"></a>全般

### <a name="what-changes-did-microsoft-announce-around-self-service-purchases-for-the-power-platform-products"></a>電源プラットフォーム製品のセルフサービス購入に関して Microsoft が発表した変更点は何ですか?

11月19日に IT 管理者は、PowerShell を使用して製品ごとにセルフサービス購入を無効にする方法を提供しました。 その使用方法については、「 [Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)」を参照してください。

この変更の準備により多くの時間を提供するために、microsoft は、すべての商用クラウドのお客様について、1月14日に power Platform 製品が Power BI を開始できるようにするための、電源プラットフォーム製品のセルフサービス購入機能のための起動を更新しています。  

2020年1月14日以降、電力プラットフォーム製品 (Power BI、電源アプリ、および電源自動化) のセルフサービス購入、サブスクリプション、およびライセンス管理の機能は、米国のコマーシャルクラウドのお客様が利用できます。 セルフサービス購入により、ユーザーは新しいテクノロジを試す機会に、より大規模な組織に最終的にメリットをもたらすソリューションを開発することができます。 現時点では、この機能は米国政府機関、非営利団体、または教育機関のテナントでは使用できません。 中央の調達および IT チームは、 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>を介してセルフサービス購入ソリューションを購入および展開するすべてのユーザーに対して可視性を持ち、PowerShell を使用して製品ごとにセルフサービス購入を無効にすることができます。

### <a name="why-is-microsoft-adding-a-self-service-purchase-option-for-the-power-platform-products"></a>Microsoft が電源プラットフォーム製品のセルフサービス購入オプションを追加するのはなぜですか?

今日の世界では、エンドユーザーと部署が、独自のテクノロジソリューションを求め、購入する機会が増えています。 これらのお客様から多数の要求を受信して、電源プラットフォーム製品のセルフサービス購入を有効にしました。 IT 管理者のニーズを均等にする一方で、組織内の個々のユーザーがサードパーティ製のソリューションを使用して知識を持たない場合に、表示や制御を行うことがよくあります。 今後の電源プラットフォーム製品のセルフサービス機能を使用すると、IT 管理者は組織内で行われているすべてのセルフサービス購入を完全に把握し、組織レベルで設定されたデータガバナンスポリシーを次のように見越計上することができるようになります。セルフサービスで購入したサブスクリプション。 また、管理者は既存のライセンスを割り当てることも、追加のサブスクリプションを購入することもできます。これには、既存の契約と、セルフサービス購入に割り当てられたユーザーの価格設定を使用します。 これらの集中的に購入したライセンスを割り当てた後、管理者は purchasers に既存のサブスクリプションをキャンセルするよう要求できます。 Microsoft は、このプロセスを今後の管理者向けに簡素化および合理化する方法を調査しています。

### <a name="which-power-platform-products-are-available-for-self-service-purchase"></a>セルフサービス購入に使用できる電源プラットフォーム製品を教えてください。

Microsoft は、米国の顧客に対して、電力プラットフォーム (Power BI、電源アプリ、および電源自動化) に対するセルフサービスの購入を開始しており、今後数か月に追加のマーケットが利用可能になりました。 現時点では、この機能は米国政府機関、非営利団体、または教育機関のテナントでは使用できません。

### <a name="will-self-service-purchase-be-enabled-for-services-beyond-the-power-platform-products"></a>電源プラットフォーム製品を超えたサービスに対してセルフサービス購入が有効になりますか?

現時点では、セルフサービス購入で提供されているのは電源プラットフォームファミリ製品のみです。

## <a name="making-a-self-service-purchase"></a>セルフサービス購入の作成

### <a name="how-does-a-customer-make-a-self-service-purchase"></a>お客様はどのようにしてセルフサービス購入を行いますか?

お客様は、Microsoft Power BI、Power Apps、および Power online の web サイトからセルフサービス購入を行うことができます。 お客様は、既存の Azure Active Directory (AD) テナント内のユーザーであることを確認するために、最初にメールアドレスを入力するように求められます。 その後、Azure AD 資格情報を使用してログインするように指示されます。 サインインした後、お客様は購入するサブスクリプションの数を選択し、クレジットカードの支払いを提供するように求められます。 購入が完了すると、サブスクリプションの使用を開始できるようになります。 また、購入者は、組織内の他のユーザーが製品を使用できるようにするための<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>の制限されたビューにアクセスすることもできます。

### <a name="what-are-the-payment-options-for-self-service-purchases"></a>セルフサービス購入の支払いオプションとは

現時点では、クレジットカードのみが利用可能な支払い方法です。 請求による支払いはサポートされていません。

### <a name="who-can-buy-through-self-service-purchase"></a>セルフサービス購入で購入できるユーザー

管理された Azure AD テナント内のゲスト以外のユーザーアカウントを持つユーザーは、購入できます。 現時点では、この機能は、官公庁、非営利団体、または教育機関のテナントでは使用できません。 これが組織に当てはまる場合は、この時点でセルフサービス購入を制御するために追加の操作は必要ありません。

セルフサービス購入の対象になっていない組織または市場のユーザーには、今日と同じように IT 管理者に連絡するように求めるメッセージが表示されます。

### <a name="can-guest-users-buy-through-self-service-purchase"></a>ゲストユーザーはセルフサービス購入で購入できますか?

いいえ、ゲストユーザーはゲストになっているテナントでセルフサービス購入を完了できません。

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a>オンプレミスの Active Directory からのユーザーの同期は、セルフサービスの購入で行うことができますか。

ユーザーが適格な Azure AD テナントにアクティブなユーザーアカウントを持っている場合は、セルフサービス購入を完了できます。

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a>セルフサービスの purchasers にライセンスを割り当てることができるユーザー

セルフサービス purchasers は、同じ Azure AD テナント内のユーザーにのみライセンスを割り当てることができます。 購入者は、ライセンスを割り当てるために、 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>の限定されたビューにアクセスできるようになります。 これらのユーザーは、表示のみが可能であり、セルフサービス購入で購入した製品にライセンスを割り当てることができます。これらのライセンスは、同じ Azure AD テナント内のユーザーに割り当てることしかできません。

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a>セルフサービスの購入者は購入を確認して管理しますか?

セルフサービス purchasers では、 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>の限定されたビューで購入を管理できます。 Purchasers は、office 365 アプリ起動ツールの [**管理**] タイルから、すべての office 365 および Dynamics online アプリに組み込まれている管理センターにいつでもアクセスできます。 作成した購入を表示したり、同じサービスに対して追加のサブスクリプションを購入したり、それらのサブスクリプションのライセンスを組織内の他のユーザーに割り当てることができます。 また、purchasers は、請求書の表示と支払い、支払い方法の更新、およびサブスクリプションのキャンセルを行うことができます。

**セルフサービス purchasers の制限された Microsoft 365 管理センターの表示:**

![Microsoft 365 管理センターのスクリーンショット。](../../media/MACBillingProductsServicesSelfServicePurchaseIW.png)

## <a name="pricing"></a>価格設定

### <a name="what-is-the-pricing-for-self-service-purchases"></a>セルフサービス購入の価格設定について

セルフサービス購入の各電源プラットフォーム製品の価格は、Microsoft の web サイトで提供されています。また、セルフサービス購入時にも、チェックアウト操作の一部として表示されます。 これらの価格は、パートナーによって集中購入または料金を提示する際に組織が支払う価格とは異なる場合があります。

### <a name="who-is-responsible-for-payment"></a>支払いの責任者

セルフサービス購入によってサブスクリプションを購入したユーザーは請求され、購入の条項と価格に基づいて支払いを担当します。

## <a name="admin-capabilities"></a>管理機能

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a>セルフサービス購入における管理者の権限を教えてください

管理者は、組織内で行われたすべてのセルフサービスの購入を<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>で確認できます。 これらのユーザーは、製品、購入者名、購入したサブスクリプション、有効期限、注文履歴、購入価格、および割り当てられたユーザーを各セルフサービス購入に対して確認できます。 電源プラットフォーム管理センターでは、管理者はセルフサービス購入容量を表示することもできます。 組織に必要な場合、管理者は、PowerShell を使用して製品ごとにセルフサービス購入を無効にすることができます。 管理者は、セルフサービス購入された製品と一元的に購入された製品に対して、同じデータ管理およびアクセスポリシーを有します。

管理者は、組織内のユーザーがセルフサービス購入を行うことができるかどうかを制御することもできます。 詳細については、「 [Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)」を参照してください。

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a>セルフサービス購入を有効にすることによって、Microsoft はデータガバナンスとコンプライアンスをどのように重視していますか?

管理者は、データガバナンスとコンプライアンスの要件に基づいて、テナント内で有効にするサービスと製品を制御します。 さらに、組織で有効になっているすべてのデータ管理とアクセスポリシーが、セルフサービスで購入可能なサービスに適用されます。

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a>セルフサービス購入から作成された製品データの所有者

セルフサービス購入で購入した製品から作成されたデータは、組織によって所有および制御されます。

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a>セルフサービス購入で行われた購入を一元管理するにはどうすればよいですか?

管理者は、既存のライセンスを割り当てることも、電源プラットフォーム製品 (Power BI、電源アプリ、および電源自動化) の追加サブスクリプションを購入することもできます。これには、既存の契約と、セルフサービス購入に割り当てられたユーザーの料金があります。 これらの集中的に購入したライセンスを割り当てた後、管理者は purchasers に既存のサブスクリプションをキャンセルするよう要求できます。 Microsoft は、このプロセスを今後の管理者向けに簡素化および合理化する方法を調査しています。

### <a name="where-does-the-admin-see-self-service-purchases"></a>管理者はどこにセルフサービス購入を表示しますか?

グローバルおよび請求管理者は、 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>のサービスを購入して購入したサブスクリプション、または中央の調達で購入されたその他のすべてのサブスクリプションを使用して、購入した**サブスクリプション** > を確認することができます。**&** 。 このリストは、中央の調達で購入されたサブスクリプションのみにフィルターを適用したり、セルフサービス購入で購入したサブスクリプションを含めることができます。

管理者は、製品、買い手名、購入したサブスクリプション、有効期限、注文履歴、購入価格、割り当てられたユーザーを表示できます。

## <a name="support-and-training"></a>サポートとトレーニング

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a>お客様の IT 部門やパートナーは、セルフサービス購入によって購入された製品をサポートすることを期待していますか。

IT 部門およびパートナーは、セルフサービス購入を通じて購入された製品に対するサポートを提供することを期待していません。 Microsoft は、セルフサービス purchasers の標準サポートを提供します。

### <a name="if-a-self-service-purchaser-calls-support-will-they-use-the-customers-premier-support-incidents"></a>セルフサービスの購入者がサポートに電話をかける場合、お客様のプレミアサポートインシデントを使用しますか?

セルフサービス purchasers では、お客様のプレミアサポートインシデントを使用してセルフサービス購入のサポートを受けることはできません。

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a>セルフサービス購入で購入した製品について、ユーザーはどのようにトレーニングを受けられるようになりますか?

ユーザー向けの豊富なトレーニングは、Microsoft Power BI、Power Apps、および Power オートメーション web サイトで提供されています。 これらの製品には、他のユーザーから直接回答やヒントを得るためのガイド学習、ドキュメント、サンプル、および強力なコミュニティが用意されています。

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a>ユーザーが組織を離れた場合、セルフサービス購入はどうなりますか?

有効なユーザーは、サブスクリプションの期間に対してセルフサービス購入を完全に使用し続けることができます。 サブスクリプションは、購入者が直接取り消すか、カスタマーサポートによってサブスクリプションをキャンセルすることを要求するまで、アクティブのままになります。 管理者は、解約されたサブスクリプションのユーザーに対して、集中購入したライセンスを割り当てることもできます。

## <a name="partners"></a>パートナー

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a>セルフサービス購入における Microsoft のパートナーの役割

管理権限を委任されたパートナーは、管理者と同様に、 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>でセルフサービス購入を表示できます。パートナーは、セルフサービス購入によって購入された製品を集中管理する組織のサポートに役立ちます。 また、パートナーは、セルフサービス購入の機能を拡張するためのソリューションを提供することができます。
