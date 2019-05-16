---
title: Contoso Corporation の非常に機密性の高いデジタル資産向けの SharePoint Online サイト
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/15/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: '概要: Contoso 社が SharePoint Online サイトを非常に規制されたデータ用に実装し、研究チーム間のコラボレーションを容易にする方法について説明します。'
ms.openlocfilehash: 99599829658e5dc46c8adebfe59f5c6d09b165de
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072784"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a>Contoso Corporation の非常に機密性の高いデジタル資産向けの SharePoint Online サイト

 **概要:** 研究チーム間のコラボレーションを容易にするために、Contoso 社が SharePoint Online サイトを高規制データ用に実装した方法。
  
Contoso 社の最も重要な資産は、独自の製造手法、開発中の製品の設計仕様など、企業秘密の形式での知的財産です。 これらのアセットはデジタル形式で、もともとは SharePoint Server 2016 サイトにファイルとして保存されています。 Contoso 社では、Microsoft 365 Enterprise を展開したときに、オンプレミスのデジタルアセットをクラウドに移行して、パリ、モスクワ、ニューヨーク、北京、Bangalore の研究チーム間で簡単にアクセスできるようにしたいと考えています。 
  
ただし、機密性の高い性質上、これらのファイルへのアクセスは次のようにする必要があります。

- SharePoint 管理者のみが管理するサイトに対する継続的なアクセス許可を持つ、それらのユーザーを表示または変更できるユーザーのセットに制限されます。 
- データ損失防止 (DLP) を使用して保護することで、ユーザーがサイト外に配布するのを防ぐことができます。
- 権限のないユーザーがサイト外に配布されている場合でも、そのコンテンツへのアクセスを許可しないように、アクセス制御リストで暗号化および保護します。

Contoso 社の IT 部門のセキュリティおよび SharePoint 管理者は、厳しく規制された[データ用に Sharepoint Online サイト](teams-sharepoint-online-sites-highly-regulated-data.md)を使用することを決定しました。
  
Contoso 社は、これらの手順を使用して、調査チームのために SharePoint Online チームサイトを作成してセキュリティ保護しています。

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a>手順 1: 研究チームグループのメンバーをレビューおよび確認する

Contoso IT 管理者は、研究チームの一連のセキュリティグループの確認を行いました。 研究者以外のユーザーを削除したか、または研究資産にアクセスする必要がないユーザーを削除しました。 

また、これらの新しいセキュリティグループも作成しました。

- **研究-管理者** アクセス許可を変更する機能を含め、サイトを完全に制御できる SharePoint 管理者のセット。
- **リサーチ-メンバー** 世界各地の研究チームの一連のセキュリティグループ。
- **リサーチ閲覧**者 サイト上の資産のみを表示できる、研究組織のエグゼクティブなどの管理ユーザーのセット。

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a>手順 2: 分離した SharePoint Online チームサイトを作成する 

Contoso 社の SharePoint 管理者は、最初に**Research**という名前の新しいチームサイトを作成しました。 その後、次のように構成します。

- リサーチの所有者の SharePoint グループを使用して、**研究管理者**のセキュリティグループをメンバーとして持つ、フルコントロールアクセス許可レベル。
- Research メンバーのセキュリティグループをメンバーとして持つ Research メンバーの SharePoint **** グループを使用するための編集アクセス許可レベル。
- リサーチ閲覧者の SharePoint グループを使用してリサーチ閲覧者のセキュリティ**** グループをメンバーとして持つ、読み取りアクセス許可レベル

その結果、SharePoint アクセス許可レベル、SharePoint グループ、およびそれらのメンバーが表示されます。

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

次に、サイトに対する追加の制限を構成しました。

構成の詳細については、「[分離した SharePoint Online チームサイトを展開する](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site)」を参照してください。

## <a name="step-3-configured-the-site-for-a-restrictive-dlp-policy"></a>手順 3: 制限付き DLP ポリシー用にサイトを構成する

最初に、Contoso 管理者は**高機密**Office 365 保持ラベルを**Research**サイトに適用しました。

次に、 **Research**という名前の新しい OFFICE 365 DLP ポリシーを作成しました。

- 非常に**機密性の高い**Office 365 保持ラベルを使用します。 
- **リサーチ**サイトに適用されます。
- ユーザーが Contoso 外の**Research**サイトでデジタルアセットを共有しようとすると、ユーザーをブロックします。

構成の詳細については、「[保持ラベルおよび DLP を使用して SharePoint Online ファイルを保護](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)する」を参照してください。

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a>手順 4: サイトの Azure Information Protection サブラベルを作成する

Contoso 管理者は、次のようなスコープ付きポリシーで、既定の**高機密**ラベルの**リサーチ**という新しい Azure Information Protection サブラベルを作成しました。

- 暗号化が必要です。
- **リサーチメンバー**セキュリティグループのメンバーによるフルアクセスを許可します。
- **リサーチ閲覧**者セキュリティグループのメンバーによる読み取りアクセスを許可します。

次に、Azure Information Protection クライアントを研究チームメンバーのデバイスに展開しました。

構成の詳細については、「 [Azure Information Protection で SharePoint Online ファイルを保護](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection)する」を参照してください。 

非常に機密性の高い資産に対する**調査**サイトの構成を次に示します。

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

**リサーチ**サイトのフォルダー内のファイルは、次の方法で保護されます。

- **Research** Azure Information Protection sublabel は、**リサーチ**サイトから移動またはコピーされたときに、ファイルと共に移動する各ファイルに暗号化と permssions を適用します。
- **リサーチ**DLP ポリシー。非常に機密性の**高い**保持ラベルと、ファイルを外部ユーザーと共有できないようにする設定を使用します。
- サイトのアクセス許可のセット。 research-Admins セキュリティグループのメンバーには、リサーチ**メンバー**およびリサーチ**閲覧****者**のセキュリティグループのメンバーへのアクセスのみが許可されます。

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a>手順 5: オンプレミスの SharePoint リサーチデータを移行する

Contoso admins は、オンプレミスの SharePoint Server 2016 サイト内のすべてのオンプレミスの研究ファイルを新しい**research** sharepoint Online サイト内のフォルダーに移動しました。

## <a name="step-6-trained-their-users"></a>手順 6: ユーザーをトレーニングする 

Contoso のセキュリティスタッフは、次の手順を実行する必須コースで研究チームをトレーニングしています。

- 新しい**Research** SharePoint Online サイトと既存のファイルにアクセスする方法について説明します。
- サイトに新しいファイルを作成し、ローカルに保存された新しいファイルをアップロードする方法。
- DLP ポリシーによって、ファイルが外部で共有されることをブロックする方法のデモ。
- Azure Information Protection クライアントを使用してリサーチファイルにリサーチサブラベル**** を付ける方法について説明します。
- サイトからリークが生じた場合でも、**リサーチ**サブラベルがファイルを保護する方法についてのデモ。

最終的には、セキュリティで保護された環境で研究者が組織全体で共同作業を行える安全な環境が得られます。 

Research サブラベルを持つ research **** ドキュメントが**research**サイトから漏洩した場合、そのドキュメントは暗号化され、有効な資格情報**** を持つ research および**research**のセキュリティグループのメンバーのみがアクセスできます。

## <a name="next-step"></a>次の手順

[展開](deploy-microsoft-365-enterprise.md)組織内の Microsoft 365 Enterprise。

