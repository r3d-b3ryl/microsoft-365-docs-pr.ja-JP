---
title: 情報バリアについて
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 情報バリアを使用して、組織内の Microsoft Teams を使用して通信のコンプライアンスを確保します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f723885a366e6f92f29faccfb632677c6e0028c8
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430225"
---
# <a name="information-barriers"></a>情報バリア

Microsoft クラウドサービスには、強力なコミュニケーションとコラボレーションの機能が含まれています。 しかし、2つのグループ間の通信とコラボレーションを制限して、組織での利益の競合を回避する必要があるとします。 または、内部情報を保護するために、組織内の特定のユーザー間のコミュニケーションとコラボレーションを制限する必要がある場合があります。 Microsoft 365 は、グループと組織間での通信とコラボレーションを可能にするため、必要に応じて特定のユーザーグループ間の通信とコラボレーションを制限する方法がありますか。 情報バリアを使用して、できることはありません。 

Microsoft Teams、SharePoint Online、OneDrive for Business では、情報バリアがサポートされるようになりました。 [サブスクリプション](#required-licenses-and-permissions)に情報の障壁が含まれている場合、コンプライアンス管理者または情報バリア管理者は、Microsoft Teams のユーザーグループ間の通信を許可または禁止するポリシーを定義できます。 情報バリアポリシーは、次のような状況で使用できます。

- 営業担当営業グループのユーザーは、マーケティングチームとファイルを通信または共有することはできません。
- 機密企業情報を扱う財務担当者は、組織内の特定のグループとファイルを通信または共有することはできません。
- 組織内の特定のグループに属するユーザーとの通信を、取引先機密資料を含む内部チームに対して行うことはできません。
- 研究チームは、製品開発チームとの通話またはオンラインチャットのみを行います。

> [!IMPORTANT]
> 情報の障壁は、2つの方法の制限***のみをサポート***します。 マーケティングなどの1つの方法の制限は、マーケティングとは通信できませんが、営業***はサポート***されていません。

これらのすべてのシナリオ例 (およびその他) については、Microsoft Teams での通信を禁止または許可するように情報バリアポリシーを定義できます。 このようなポリシーを使用すると、ユーザーが不要な通話やチャットを行うことができなくなり、Microsoft Teams 内の特定のグループとのみ通信できるようになります。 情報バリアポリシーが有効になっていると、そのポリシーの対象となっているユーザーが Microsoft Teams 内の他のユーザーと通信しようとするたびに、チェックが行われて、通信 (情報バリアポリシーによって定義されている) を回避 (または許可) します。 情報の障壁に関するユーザーの作業の詳細については、「 [Microsoft Teams の情報障壁](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)」を参照してください。

> [!IMPORTANT]
> 現時点では、情報バリアは電子メール通信には適用されません。 さらに、情報バリアは、[コンプライアンスの境界](set-up-compliance-boundaries.md)から独立しています。<p>情報バリアポリシーを定義して適用する前に、組織の[Exchange アドレス帳ポリシー](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)が有効になっていないことを確認してください。 (情報障壁はアドレス帳ポリシーに基づいています。) 

## <a name="what-happens-with-information-barriers"></a>情報バリアで行われる処理

情報バリアポリシーが設定されている場合、他の特定のユーザーとのファイルの通信または共有を行わないユーザーは、それらのユーザーを検索、選択、チャット、または呼び出すことができません。 情報バリアを使用して、承認されていない通信を防止するためのチェックが行われます。

最初は、情報の障壁は Microsoft Teams のチャットおよびチャネルにのみ適用されます。 Microsoft Teams では、情報バリア ポリシーは、次の種類の無許可の通信を決定し、防止します。

- ユーザーの検索
- チームにメンバーを追加する
- 他のユーザーとのチャット セッションを開始する
- グループ チャットを開始する
- ユーザーを会議に招待する
- 画面を共有する
- 電話をかける
- 別のユーザーとファイルを共有する
- 共有リンクによるファイルへのアクセス 

関係するユーザーが、活動を防止する情報バリア ポリシーに含まれている場合、続行できません。 さらに、情報バリア ポリシーに含まれているすべてのユーザーは、Microsoft Teams で他のユーザーと通信できないようにすることができます。 情報バリア ポリシーの影響を受けるユーザーが同じチームまたはグループ チャットの一部である場合、それらのユーザーがチャット セッションから削除され、グループとのそれ以上の通信が許可されないことがあります。

情報の障壁に関するユーザーの作業の詳細については、「 [Microsoft Teams の情報障壁](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)」を参照してください。

## <a name="required-licenses-and-permissions"></a>必要なライセンスとアクセス許可

情報バリアは現在ロールアウトされており、次のようなサブスクリプションに含まれています。

- Microsoft 365 E5/A5
- Office 365 E5/A5
- Office 365 Advanced Compliance
- Microsoft 365 コンプライアンス E5/A5
- Microsoft 365 Insider リスク管理

詳細については、「[コンプライアンスソリューション](https://products.office.com/business/security-and-compliance/compliance-solutions)」を参照してください。

[情報バリアポリシーを定義または編集](information-barriers-policies.md)するには、次のいずれかの役割が割り当てられている必要があります。

- Microsoft 365 グローバル管理者
- Office 365 グローバル管理者
- コンプライアンス管理者
- IB コンプライアンス管理 (新しい役割)

役割とアクセス許可の詳細については、「 [Office 365 セキュリティ & コンプライアンスセンターのアクセス許可](../security/office-365-security/protect-against-threats.md)」を参照してください。

情報バリアポリシーを定義、検証、または編集するには、PowerShell コマンドレットを熟知している必要があります。 [「How to](information-barriers-policies.md)」の記事では PowerShell コマンドレットの例をいくつか示していますが、パラメーターなどの追加の詳細については、組織のために知っておく必要があります。

## <a name="next-steps"></a>次の手順

- [Microsoft Teams の情報障壁の詳細を知る](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)
- [情報バリアポリシーに使用できる属性を参照してください。](information-barriers-attributes.md)
- [情報バリアのポリシーを定義する](information-barriers-policies.md)
- [情報バリア ポリシーの編集 (または削除)](information-barriers-edit-segments-policies.md)
- [SharePoint Online の情報障壁の詳細を知る](https://docs.microsoft.com/sharepoint/information-barriers)
- [OneDrive for business の情報障壁の詳細を知る](https://docs.microsoft.com/onedrive/information-barriers)