---
title: Microsoft 365 の情報障壁について
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
localization_priority: None
description: 情報バリアを使用して、組織内で Microsoft Teams を使用して通信コンプライアンスを確保します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 73a76e67fdb96f89dbd11daf4b2ef12f6590f92a
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701006"
---
# <a name="learn-about-information-barriers-in-microsoft-365"></a>Microsoft 365 の情報障壁について

Microsoft クラウド サービスには、強力な通信機能とコラボレーション機能が含まれます。 ただし、組織内で関心の競合が発生しないように、2 つのグループ間の通信とコラボレーションを制限するとします。 または、内部情報を保護するために、組織内の特定のユーザー間の通信とコラボレーションを制限したい場合があります。 Microsoft 365 を使用すると、グループや組織間でのコミュニケーションとコラボレーションが可能になります。そのため、必要に応じて、特定のユーザー グループ間の通信とコラボレーションを制限する方法はありますか? 情報バリアを使用すると、可能です。 

Microsoft Teams、SharePoint Online、OneDrive for Business で情報バリアがサポートされました。 サブスクリプションに [情報](#required-licenses-and-permissions) バリアが含まれる場合、コンプライアンス管理者または情報障壁管理者は、Microsoft Teams のユーザー グループ間の通信を許可または防止するポリシーを定義できます。 情報バリア ポリシーは、次のような状況で使用できます。

- 一日の業者グループのユーザーは、マーケティング チームと通信したり、ファイルを共有したりしなけず
- 会社の機密情報に取り組む財務担当者は、組織内の特定のグループとファイルを通信したり共有したりしなき
- 営業秘密資料を持つ内部チームは、組織内の特定のグループのユーザーに電話したり、オンラインでチャットしたりしなき
- 研究チームは、製品開発チームに電話するか、オンラインでチャットする必要があります。

> [!IMPORTANT]
> 情報バリア * は **_ 2** つの方法の制限のみをサポートします。 マーケティングなどの一方的な制限は、日の業者と通信できますが、日の業者はマーケティング _* と通信できません** は _サポート_ されていません。

これらのすべてのシナリオ例 (およびそれ以上) では、Microsoft Teams での通信を防止または許可する情報バリア ポリシーを定義できます。 このようなポリシーを使用すると、ユーザーが通話やチャットを行わないか、Microsoft Teams の特定のグループとのみ通信できます。 情報バリア ポリシーが有効な場合、それらのポリシーの対象となるユーザーが Microsoft Teams の他のユーザーと通信しようとするたびに、(情報バリア ポリシーで定義されている) 通信を防止 (または許可) するためのチェックが行われます。 情報障壁のあるユーザー エクスペリエンスの詳細については [、Microsoft Teams の情報バリアを参照してください](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。

> [!IMPORTANT]
> 現在、情報バリアは電子メール通信には適用されません。 さらに、情報バリアはコンプライアンスの境界 [から独立しています](set-up-compliance-boundaries.md)。<p>情報バリア ポリシーを定義して適用する前に、組織に Exchange アドレス帳ポリシーが [有効で](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) なされていないことを確認してください。 (情報バリアはアドレス帳ポリシーに基づく) 

## <a name="what-happens-with-information-barriers"></a>情報バリアの発生

情報バリア ポリシーが適用されている場合、他の特定のユーザーとファイルの通信や共有を行う必要のあるユーザーは、それらのユーザーの検索、選択、チャット、または呼び出しを行うことはありません。 情報バリアを使用して、承認されていない通信を防止するためのチェックが行われます。

最初は、情報バリアは Microsoft Teams のチャットとチャネルにのみ適用されます。 Microsoft Teams では、情報バリア ポリシーは、次の種類の無許可の通信を決定し、防止します。

- ユーザーの検索
- チームにメンバーを追加する
- 他のユーザーとのチャット セッションを開始する
- グループ チャットを開始する
- ユーザーを会議に招待する
- 画面を共有する
- 電話をかける
- 別のユーザーとファイルを共有する
- 共有リンクを使用してファイルにアクセスする 

関係するユーザーが、活動を防止する情報バリア ポリシーに含まれている場合、続行できません。 さらに、情報バリア ポリシーに含まれているすべてのユーザーは、Microsoft Teams で他のユーザーと通信できないようにすることができます。 情報バリア ポリシーの影響を受けるユーザーが同じチームまたはグループ チャットの一部である場合、それらのユーザーがチャット セッションから削除され、グループとのそれ以上の通信が許可されないことがあります。

情報障壁のあるユーザー エクスペリエンスの詳細については [、Microsoft Teams の情報バリアを参照してください](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。

## <a name="required-licenses-and-permissions"></a>必要なライセンスとアクセス許可

情報バリアは現在展開中であり、次のようなサブスクリプションに含まれています。

- Microsoft 365 E5/A5
- Office 365 E5/A5
- Office 365 Advanced Compliance
- Microsoft 365 コンプライアンス E5/A5
- Microsoft 365 Insider Risk Management

詳細については、セキュリティとコンプライアンス [に関する Microsoft 365 ライセンス ガイダンス&覧ください](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)。

情報 [バリア ポリシーを定義または編集するには、](information-barriers-policies.md)次のいずれかの役割が割り当てられている必要があります。

- Microsoft 365 グローバル管理者
- Office 365 グローバル管理者
- コンプライアンス管理者
- IB コンプライアンス管理 (これは新しい役割です)

(役割とアクセス許可の詳細については、「Office [365 セキュリティ](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)/コンプライアンス センター&アクセス許可」を参照してください)。

情報バリア ポリシーを定義、検証、または編集するには、PowerShell コマンドレットに精通している必要があります。 方法に関する記事では PowerShell コマンドレットのいくつかの例[](information-barriers-policies.md)を示しますが、組織のパラメーターなど、追加の詳細を知る必要があります。

## <a name="next-steps"></a>次の手順

- [Microsoft Teams の情報障壁の詳細](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)
- [情報バリア ポリシーに使用できる属性を確認する](information-barriers-attributes.md)
- [情報バリアのポリシーを定義する](information-barriers-policies.md)
- [情報バリア ポリシーの編集 (または削除)](information-barriers-edit-segments-policies.md)
- [SharePoint Online の情報バリアの詳細](https://docs.microsoft.com/sharepoint/information-barriers)
- [OneDrive for Business の情報バリアの詳細](https://docs.microsoft.com/onedrive/information-barriers)