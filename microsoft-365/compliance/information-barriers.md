---
title: Microsoft 365 の情報障壁について
description: 情報バリアを使用して、組織内で Microsoft Teams を使用して通信コンプライアンスを確保します。
ms.author: robmazz
author: robmazz
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
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 003347d46bed2529831a92681e73630d58a1f653
ms.sourcegitcommit: 8d28bce1a3445878b066864e766cf52cb83becd1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/02/2021
ms.locfileid: "50071272"
---
# <a name="learn-about-information-barriers-in-microsoft-365"></a>Microsoft 365 の情報障壁について

Microsoft クラウド サービスには、強力な通信機能とコラボレーション機能が含まれます。 ただし、組織内で関心の競合が発生しないように、2 つのグループ間の通信とコラボレーションを制限するとします。 または、内部情報を保護するために、組織内の特定のユーザー間の通信とコラボレーションを制限したい場合があります。 Microsoft 365 を使用すると、グループや組織間でのコミュニケーションとコラボレーションが可能になります。そのため、必要に応じて、特定のユーザー グループ間の通信とコラボレーションを制限する方法はありますか? 情報バリアを使用すると、次の方法を使用できます。

Microsoft Teams、SharePoint Online、OneDrive for Business は情報障壁をサポートしています。 サブスクリプションに [情報](#required-licenses-and-permissions) バリアが含まれる場合、コンプライアンス管理者、または情報障壁管理者は、Microsoft Teams のユーザー グループ間の通信を許可または防止するポリシーを定義できます。 情報バリア ポリシーは、次のような状況で使用できます。

- その日の業者グループのユーザーは、マーケティング チームと通信したり、ファイルを共有したりしなけず
- 会社の機密情報に取り組む財務担当者は、組織内の特定のグループとファイルを通信したり共有したりしなき
- 営業秘密資料を持つ内部チームは、組織内の特定のグループのユーザーに電話したり、オンラインでチャットしたりしなき
- 研究チームは、製品開発チームにオンラインでのみ電話またはチャットを行う必要があります。
- day trader グループのサイトは、day trader グループ外のユーザーが共有したり、アクセスしたりしてみることができます。

> [!IMPORTANT]
> 情報バリア * は **_ 2** つの方法の制限のみをサポートします。 マーケティングなどの 1 つの方法の制限は、日の業者と通信および共同作業できますが、日の業者はマーケティング _* と通信および共同作業を行う機能は _サポート_ されていません**。

これらのすべてのシナリオ例 (およびそれ以上) では、Microsoft Teams、SharePoint Online、OneDrive での通信とコラボレーションを防止または許可する情報バリア ポリシーを定義できます。 このようなポリシーを使用すると、ユーザーが通話やチャットを行わないか、Microsoft Teams の特定のグループとのみ通信できます。 情報バリア ポリシーが有効な場合、これらのポリシーの対象となるユーザーが Microsoft Teams の他のユーザーとの通信と共同作業を試みるたびに、SharePoint Online または OneDrive のチェックは、(情報バリア ポリシーで定義されている) 通信とコラボレーションを防止 (または許可) するために行われます。

情報バリアを備えるユーザー エクスペリエンスの詳細については、以下を参照してください。

- [Microsoft Teams の情報障壁](/MicrosoftTeams/information-barriers-in-teams)
- [SharePoint Online の情報障壁](/sharepoint/information-barriers)
- [OneDrive の情報バリア](/onedrive/information-barriers)

> [!IMPORTANT]
> 現在、情報バリアは電子メール通信には適用されません。 さらに、情報バリアはコンプライアンスの境界 [から独立しています](set-up-compliance-boundaries.md)。<p> 情報バリア ポリシーを定義して適用する前に、組織に Exchange アドレス帳ポリシーが有効でなされていないこと [を](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) 確認してください。 (情報バリアはアドレス帳ポリシーに基づく)

## <a name="what-happens-with-information-barriers"></a>情報バリアの発生

情報バリア ポリシーが適用されている場合、他の特定のユーザーとファイルの通信や共有を行う必要のあるユーザーは、それらのユーザーの検索、選択、チャット、または呼び出しを行うことはありません。 情報バリアにより、不正な通信とコラボレーションを防止するためにチェックが実施されます。 

情報バリアは、Microsoft Teams (チャットとチャネル)、SharePoint Online、OneDrive に適用されます。 Microsoft Teams では、情報バリア ポリシーは、次の種類の無許可の通信を決定し、防止します。

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

情報障壁のあるユーザー エクスペリエンスの詳細については [、Microsoft Teams の情報バリアを参照してください](/MicrosoftTeams/information-barriers-in-teams)。

SharePoint Online と OneDrive では、情報バリア ポリシーによって、次の種類の未承認のコラボレーションが決定され、防止されます。

- サイトへのメンバーの追加
- ユーザーによるサイトまたはコンテンツへのアクセス
- サイトまたはコンテンツを別のユーザーと共有する
- サイトの検索

情報バリアを備えるユーザー エクスペリエンスの詳細については、SharePoint Online の情報バリア [を参照してください。](/sharepoint/information-barriers)

## <a name="required-licenses-and-permissions"></a>必要なライセンスとアクセス許可

情報バリアは現在展開中であり、次のようなサブスクリプションに含まれています。

- Microsoft 365 E5/A5
- Office 365 E5/A5
- Office 365 Advanced Compliance
- Microsoft 365 コンプライアンス E5/A5
- Microsoft 365 Insider Risk Management

詳細については、セキュリティとコンプライアンス [に関する Microsoft 365 ライセンス ガイダンス&してください](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)。

情報 [バリア ポリシーを定義または編集するには、](information-barriers-policies.md)次のいずれかの役割が割り当てられている必要があります。

- Microsoft 365 グローバル管理者
- Office 365 グローバル管理者
- コンプライアンス管理者
- IB コンプライアンス管理

(役割とアクセス許可の詳細については、「Office [365 セキュリティ](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)/コンプライアンス センター&アクセス許可」を参照してください)。

情報バリア ポリシーを定義、検証、または編集するには、PowerShell コマンドレットに精通している必要があります。 手順に関する記事には PowerShell コマンドレットの例[](information-barriers-policies.md)がいくつか示されています。ただし、組織のパラメーターなど、その他の詳細を知る必要があります。

## <a name="next-steps"></a>次の手順

- [Microsoft Teams の情報障壁の詳細](/MicrosoftTeams/information-barriers-in-teams)
- [SharePoint Online の情報バリアの詳細](/sharepoint/information-barriers)
- [OneDrive の情報バリアの詳細](/onedrive/information-barriers)
- [情報バリア ポリシーに使用できる属性を確認する](information-barriers-attributes.md)
- [情報バリアのポリシーを定義する](information-barriers-policies.md)
- [情報バリア ポリシーの編集 (または削除)](information-barriers-edit-segments-policies.md)