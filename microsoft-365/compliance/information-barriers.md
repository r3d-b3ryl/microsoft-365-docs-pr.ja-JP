---
title: 情報バリアについての詳細情報
description: Microsoft Purview の情報バリアについて説明します。
keywords: Microsoft 365、Microsoft Purview、コンプライアンス、情報バリア
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
ms.localizationpriority: ''
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 72a53580222b315f86fd397e391b026937b8035b
ms.sourcegitcommit: 5c64002236561000c5bd63c71423e8099e803c2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2022
ms.locfileid: "65287180"
---
# <a name="learn-about-information-barriers"></a>情報バリアについての詳細情報

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft クラウド サービスには、強力なコミュニケーションおよびコラボレーション機能が搭載されています。 ただし、組織内で競合が発生しないように、2 つのグループ間の通信とコラボレーションを制限するとします。 または、内部情報を保護するために、組織内の特定のユーザー間のコミュニケーションとコラボレーションを制限したい場合もあります。 Microsoft 365では、グループや組織間のコミュニケーションとコラボレーションが可能になるため、必要に応じて特定のユーザー グループ間の通信とコラボレーションを制限する方法はありますか? Microsoft Purview Information Barriers (IB) を使用すると、次のことができます。

Microsoft Teams、SharePoint Online、およびOneDrive for Businessは、情報バリアをサポートします。 [サブスクリプション](#required-licenses-and-permissions)に情報バリア、コンプライアンス管理者、または情報バリアが含まれていると仮定すると、管理者は、Microsoft Teams内のユーザーグループ間の通信を許可または禁止するポリシーを定義できます。 情報バリア ポリシーは、次のような状況で使用できます。

- その日のトレーダー グループのユーザーは、マーケティング チームとファイルを通信したり共有したりしないでください
- 会社の機密情報に取り組む財務担当者は、組織内の特定のグループとファイルを通信したり共有したりしないでください
- 営業秘密資料を持つ内部チームは、組織内の特定のグループのユーザーとオンラインで通話したりチャットしたりしないでください。
- リサーチ チームは、製品開発チームとオンラインでのみ通話またはチャットする必要があります
- 日の取引グループのサイトは、その日の取引グループ以外のユーザーが共有したりアクセスしたりしないでください。

> [!IMPORTANT]
> 情報バリア ***唯一のサポート** _ 双方向の制限。 マーケティングなどの一方向の制限では、日次業者と通信して共同作業できますが、日次業者はマーケティング _*と通信して共同作業 _することはできません_**。

これらのシナリオ例 (およびその他) のすべてについて、情報バリア ポリシーを定義して、Microsoft Teams、SharePoint Online、OneDriveでの通信とコラボレーションを防止または許可することができます。 このようなポリシーを使用すると、ユーザーが不要なユーザーと通話またはチャットしたり、Microsoft Teams内の特定のグループとのみ通信したりできなくなります。 情報バリア ポリシーが有効になっている場合、これらのポリシーの対象となるユーザーがMicrosoft Teamsで他のユーザーと通信および共同作業を行おうとするたびに、SharePoint Online またはOneDriveチェックが行われ、(情報バリア ポリシーによって定義される) 通信とコラボレーションが防止 (または許可) されます。

情報バリアに関するユーザー エクスペリエンスの詳細については、次を参照してください。

- [Microsoft Teams の情報バリア](/MicrosoftTeams/information-barriers-in-teams)
- [SharePoint Online の情報バリア](/sharepoint/information-barriers)
- [OneDriveの情報バリア](/onedrive/information-barriers)

> [!IMPORTANT]
> 現時点では、情報バリアは電子メール通信には適用されません。 さらに、情報バリアは [コンプライアンスの境界](set-up-compliance-boundaries.md)から独立しています。<p> 情報バリア ポリシーを定義して適用する前に、組織に[Exchangeアドレス帳ポリシー](/exchange/address-books/address-book-policies/address-book-policies)が有効になっていないことを確認してください。 (情報バリアはアドレス帳ポリシーに基づいています。

## <a name="what-happens-with-information-barriers"></a>情報バリアで何が起こるか

情報バリア ポリシーが適用されている場合、他の特定のユーザーとファイルを通信したり共有したりすべきでないユーザーは、それらのユーザーを検索、選択、チャット、または呼び出すことはできません。 情報バリアにより、不正な通信とコラボレーションを防ぐためのチェックが行われます。

情報バリアは、Microsoft Teams (チャットとチャネル)、SharePoint Online、OneDriveに適用されます。 Microsoft Teams では、情報バリア ポリシーは、次の種類の無許可の通信を決定し、防止します。

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

情報バリアに関するユーザー エクスペリエンスの詳細については、[Microsoft Teamsの情報バリアに関するページを](/MicrosoftTeams/information-barriers-in-teams)参照してください。

SharePoint Online およびOneDriveでは、情報バリア ポリシーによって、次の種類の承認されていないコラボレーションが決定され、防止されます。

- サイトへのメンバーの追加
- ユーザーによるサイトまたはコンテンツへのアクセス
- 別のユーザーとサイトまたはコンテンツを共有する
- サイトの検索

情報バリアに関するユーザー エクスペリエンスの詳細については、「[SharePoint Online の情報バリア](/sharepoint/information-barriers)」を参照してください。

## <a name="required-licenses-and-permissions"></a>必要なライセンスとアクセス許可

IB の使用を開始する前に、[Microsoft 365 サブスクリプション](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)とアドオンを確認する必要があります。 IB にアクセスして使用するには、組織に次のいずれかのサブスクリプションまたはアドオンが必要です。

- Microsoft 365 E5/A5 サブスクリプション (有料または試用版)
- Office 365 E5/A5/A3/A1 サブスクリプション (有料または試用版)
- Office 365 Advanced Compliance アドオン (新しいサブスクリプションでは使用できなくなります)
- Microsoft 365 E3/A3/A1 サブスクリプション + Microsoft 365 E5/A5 コンプライアンス アドオン
- Microsoft 365 E3/A3/A1 サブスクリプション + Microsoft 365 E5/A5 Insider Risk Management アドオン

詳細については、[セキュリティ&コンプライアンスに関するMicrosoft 365ライセンスガイダンスに関するページを](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)参照してください。

[情報バリア ポリシーを定義または編集](information-barriers-policies.md)するには、次のいずれかのロールを割り当てる必要があります。

- Microsoft 365 グローバル管理者
- Office 365 グローバル管理者
- コンプライアンス管理者
- IB コンプライアンス管理

(ロールとアクセス許可の詳細については、「[Office 365 セキュリティ & コンプライアンス センターのアクセス許可](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)」を参照してください)。

情報バリア ポリシーを定義、検証、または編集するには、PowerShell コマンドレットに精通している必要があります。 方法に関する [記事](information-barriers-policies.md)では PowerShell コマンドレットの例をいくつか紹介していますが、組織のパラメーターなどのその他の詳細を把握しておく必要があります。

## <a name="next-steps"></a>次の手順

- [Microsoft Teamsの情報バリアの詳細を確認する](/MicrosoftTeams/information-barriers-in-teams)
- [SharePoint Online の情報バリアの詳細](/sharepoint/information-barriers)
- [OneDriveの情報バリアの詳細を確認する](/onedrive/information-barriers)
- [情報バリア ポリシーに使用できる属性を確認する](information-barriers-attributes.md)
- [情報バリアに対するポリシーを定義する](information-barriers-policies.md)
- [情報バリア ポリシーの編集 (または削除)](information-barriers-edit-segments-policies.md)
