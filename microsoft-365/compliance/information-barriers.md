---
title: Microsoft 365 の情報バリアの詳細
description: 組織内の Microsoft Teams を使用して通信コンプライアンスを確保するには、情報バリアを使用します。
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
ms.openlocfilehash: 4ef3fce82a10792c8289a4a3c4e3cb5639a4d178
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051879"
---
# <a name="learn-about-information-barriers-in-microsoft-365"></a>Microsoft 365 の情報バリアの詳細

Microsoft クラウド サービスには、強力なコミュニケーションおよびコラボレーション機能が搭載されています。 ただし、組織内で利益相反が発生しないように、2 つのグループ間の通信とコラボレーションを制限するとします。 または、内部情報を保護するために、組織内の特定のユーザー間の通信とコラボレーションを制限する必要がある場合があります。 Microsoft 365 では、グループや組織間でのコミュニケーションとコラボレーションが可能なので、必要に応じて特定のグループのユーザー間の通信とコラボレーションを制限する方法はありますか? 情報バリアを使用すると、次の機能を使用できます。

Microsoft Teams、SharePoint Online、OneDrive for Business では、情報バリアがサポートされています。 サブスクリプションに [情報](#required-licenses-and-permissions) バリアが含まれると仮定すると、コンプライアンス管理者、または情報バリア管理者は、Microsoft Teams のユーザー グループ間の通信を許可または防止するポリシーを定義できます。 情報バリア ポリシーは、次のような状況で使用できます。

- 当日のトレーダー グループのユーザーは、マーケティング チームとファイルの通信や共有を行う必要があります。
- 会社の機密情報に取り組む財務担当者は、組織内の特定のグループとファイルを通信したり共有したりしな
- 営業秘密資料を持つ内部チームは、組織内の特定のグループのユーザーとオンラインで通話したりチャットしたりしな
- リサーチ チームは、製品開発チームとオンラインでのみ通話またはチャットする必要があります。
- デイ トレーダー グループのサイトは、その日のトレーダー グループ外のユーザーが共有したり、アクセスしたりしな

> [!IMPORTANT]
> 情報バリア * は **、** _ 2 つの方法の制限のみをサポートします。 マーケティングなどの 1 つの方法の制限は、デイ トレーダーと通信および共同作業できますが、デイ トレーダーはマーケティング _* と通信および共同作業することはできません **は _サポート_ されていません。

これらすべてのシナリオ例 (およびそれ以上) に関して、Microsoft Teams、SharePoint Online、OneDrive での通信およびコラボレーションを防止または許可するために、情報バリア ポリシーを定義できます。 このようなポリシーを使用すると、ユーザーが通話やチャットを行わないか、Microsoft Teams の特定のグループとのみ通信できます。 情報バリア ポリシーが有効な場合、これらのポリシーの対象となるユーザーが Microsoft Teams で他のユーザーとの通信と共同作業を試みるたびに、SharePoint Online または OneDrive のチェックは、(情報バリア ポリシーで定義されている) 通信とコラボレーションを防止 (または許可) するために行われます。

情報バリアに関するユーザー エクスペリエンスの詳細については、以下を参照してください。

- [Microsoft Teams の情報バリア](/MicrosoftTeams/information-barriers-in-teams)
- [SharePoint Online の情報バリア](/sharepoint/information-barriers)
- [OneDrive の情報バリア](/onedrive/information-barriers)

> [!IMPORTANT]
> 現在、情報バリアは電子メール通信には適用されません。 さらに、情報バリアはコンプライアンスの境界 [とは独立しています](set-up-compliance-boundaries.md)。<p> 情報バリア ポリシーを定義して適用する前に、組織に Exchange アドレス帳ポリシーが適用されていないこと [を](/exchange/address-books/address-book-policies/address-book-policies) 確認してください。 (情報バリアはアドレス帳ポリシーに基づいて設定されます。

## <a name="what-happens-with-information-barriers"></a>情報バリアで何が起こるか

情報バリア ポリシーが適用されている場合、他の特定のユーザーとファイルを通信したり共有したりしなき人は、それらのユーザーを見つけたり、選択したり、チャットしたり、呼び出したりできない。 情報バリアにより、不正な通信やコラボレーションを防止するチェックが実施されています。 

情報バリアは、Microsoft Teams (チャットとチャネル)、SharePoint Online、OneDrive に適用されます。 Microsoft Teams では、情報バリア ポリシーは、次の種類の無許可の通信を決定し、防止します。

- ユーザーの検索
- チームにメンバーを追加する
- 他のユーザーとのチャット セッションを開始する
- グループ チャットを開始する
- ユーザーを会議に招待する
- 画面を共有する
- 電話をかける
- 別のユーザーとファイルを共有する
- 共有リンクを使用したファイルへのアクセス

関係するユーザーが、活動を防止する情報バリア ポリシーに含まれている場合、続行できません。 さらに、情報バリア ポリシーに含まれているすべてのユーザーは、Microsoft Teams で他のユーザーと通信できないようにすることができます。 情報バリア ポリシーの影響を受けるユーザーが同じチームまたはグループ チャットの一部である場合、それらのユーザーがチャット セッションから削除され、グループとのそれ以上の通信が許可されないことがあります。

情報バリアに関するユーザー エクスペリエンスの詳細については [、「Microsoft Teams の情報バリア」を参照してください](/MicrosoftTeams/information-barriers-in-teams)。

SharePoint Online および OneDrive では、情報バリア ポリシーによって、次の種類の未承認のコラボレーションが決定され、防止されます。

- サイトへのメンバーの追加
- ユーザーによるサイトまたはコンテンツへのアクセス
- サイトまたはコンテンツを別のユーザーと共有する
- サイトの検索

情報バリアに関するユーザー エクスペリエンスの詳細については、「SharePoint Online の情報バリア [」を参照してください。](/sharepoint/information-barriers)

## <a name="required-licenses-and-permissions"></a>必要なライセンスとアクセス許可

情報バリアは現在展開中で、次のようなサブスクリプションに含まれています。

- Microsoft 365 E5/A5
- Office 365 E5/A5
- Office 365 Advanced Compliance
- Microsoft 365 コンプライアンス E5/A5
- Microsoft 365 Insider リスク管理

詳細については [、「Microsoft 365 & ライセンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)ガイダンス」を参照してください。

情報 [バリア ポリシーを定義または編集するには](information-barriers-policies.md)、次のいずれかの役割を割り当てる必要があります。

- Microsoft 365 グローバル管理者
- Office 365 グローバル管理者
- コンプライアンス管理者
- IB コンプライアンス管理

(役割とアクセス許可の詳細については、「Office [365 Security](../security/defender-365-security/permissions-in-the-security-and-compliance-center.md)& コンプライアンス センター」を参照してください。

情報バリア ポリシーを定義、検証、または編集するには、PowerShell コマンドレットに精通している必要があります。 方法に関する記事では、PowerShell コマンドレットのいくつかの例[](information-barriers-policies.md)を示しますが、組織のパラメーターなど、他の詳細を知る必要があります。

## <a name="next-steps"></a>次のステップ

- [Microsoft Teams の情報バリアの詳細](/MicrosoftTeams/information-barriers-in-teams)
- [SharePoint Online の情報バリアの詳細](/sharepoint/information-barriers)
- [OneDrive の情報バリアの詳細](/onedrive/information-barriers)
- [情報バリア ポリシーに使用できる属性を確認する](information-barriers-attributes.md)
- [情報バリアのポリシーを定義する](information-barriers-policies.md)
- [情報バリア ポリシーの編集 (または削除)](information-barriers-edit-segments-policies.md)