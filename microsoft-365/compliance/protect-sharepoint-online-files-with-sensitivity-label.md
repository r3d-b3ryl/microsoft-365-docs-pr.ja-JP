---
title: 機密度ラベルで SharePoint Online ファイルを保護する
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.custom:
- Ent_Solutions
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: '概要: Azure Information Protection を適用して、機密性の高い SharePoint Online チーム サイト内のファイルを保護します。'
ms.openlocfilehash: 8d802d8c2b5202e51089659264b2e2c14f14ad3d
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214631"
---
# <a name="protect-sharepoint-online-files-with-a-sensitivity-label"></a>機密度ラベルで SharePoint Online ファイルを保護する

この記事の手順を使用して、秘密度ラベルを構成し、ファイルの暗号化とアクセス許可を提供します。 これらのファイルは、非常に機密性の高い社外秘の保護のため構成されている SharePoint ライブラリに追加できます。 または、サイトから直接ファイルを開き、ラベルを適用できます。 暗号化およびアクセス許可の保護は、ファイルをサイトからダウンロードした場合にも適用されます。 

これらの手順は、SharePoint サイトとそれらのサイト内のファイルの高度な機密保護を構成するための大きなソリューションの一部です。詳細については、「[SharePoint Online サイトとファイルをセキュリティで保護する](../security/office-365-security/secure-sharepoint-online-sites-and-files.md)」を参照してください。 

SharePoint Online 内のファイルに機密度ラベルを使用することは、すべてのお客様に推奨されるものではなく、ファイルの一部に対してこの保護レベルを必要としているお客様向けのオプションです。

このソリューションに関する重要な注意点がいくつかあります:
- 組織が[ SharePoint および OneDrive の Office ファイルに対する機密ラベルを有効にしていない場合 (パブリック プレビュー)](/microsoft-365/compliance/sensitivity-labels-sharepoint-onedrive-files): 暗号化が Office 365 に保存されているファイルに適用されている場合、このサービスはこれらのファイルのコンテンツを処理することはできません。 共同編集、電子情報開示、検索、Delve、その他の共同作業機能は機能しません。 データ損失防止 (DLP) ポリシーはメタデータ (ラベルを含む) でのみ機能し、これらのファイルのコンテンツ (ファイル内のクレジットカード番号など) には機能しません。

- このソリューションでは、ユーザーは保護を適用するラベルを選択する必要があります。 自動暗号化と SharePoint がファイルにインデックスを付け検査する機能を要求するには、SharePoint Online で Information Rights Management (IRM) を使用することを検討してください。 IRM の SharePoint ライブラリを構成する場合、ファイルが編集のためにダウンロードされるときに、自動的に暗号化されます。  SharePoint IRM には、決定に影響を与える可能性のある制限が含まれます。 詳細については、「[SharePoint 管理センターにおける Information Rights Management (IRM) の設定](https://docs.microsoft.com/microsoft-365/compliance/set-up-irm-in-sp-admin-center)」を参照してください。

## <a name="admin-setup"></a>管理者セットアップ

特定の SharePoint Online チーム サイトで、ファイルに対してこの追加レベルのセキュリティ保護を行うには、サイト独自のラベル、または厳しく規制されたデータの一般的なラベルのサブラベルのいずれかである、カスタマイズされた機密ラベルを構成する必要があります。 SharePoint Online チーム サイトの Microsoft 365 グループのメンバーにだけ、カスタマイズされたラベルまたはサブラベルがラベルのリストに表示されます。

- 全体での使用と個別のプライベート チームの両方に対して少ない数のラベルが必要な場合は、機密ラベルを使用します。

- ラベルを多数使用している場合、または機密性の高いチーム用のラベルを機密性の高いファイルの汎用ラベルの下でまとめる場合は、機密サブラベルを使用します。

[こちらの手順](encryption-sensitivity-labels.md)を使用して、別のラベルまたはサブラベルを次の設定で構成します。

- ラベルまたはサブラベルの名前には、チーム サイトの名前が含まれている
- 暗号化が有効になっています
- チーム サイトの Microsoft 365 グループに、共同作成者のアクセス許可が与えられている

作成した後、ユーザーのために新しいラベルまたはサブラベルを発行します。ユーザーは、それらをローカルでチームにアップロードする前、またはチームに保存された後にファイルに適用できます。
 
Microsoft Word、Excel、PowerPoint の [**ホーム**] リボンの [**機密度**] のオプションから機密度ラベルを選択できます。
  
> [!NOTE]
> 機密性の高い SharePoint Online チーム サイトが複数ある場合は、複数の機密度ラベルを作成する必要があります。 
  
## <a name="adding-permissions-for-external-users"></a>外部ユーザーに対するアクセス許可の追加
機密ラベルで保護されているファイルへのアクセス権を外部ユーザーに付与するには 2 つの方法があります。 どちらの場合も、外部ユーザーには Azure AD アカウントが必要です。 外部ユーザーが Azure AD を使用する組織のメンバーではない場合、サインアップ ページ ([https://aka.ms/aip-signup](https://aka.ms/aip-signup)) を使用して個人で Azure AD アカウントを取得できます。

 - チーム サイトの Microsoft 365 グループに外部ユーザーを追加します。 最初に、自分のディレクトリに B2B ユーザーとしてのアカウントを追加する必要があります。 [Azure Rights Management によるグループ メンバーシップのキャッシュ](https://docs.microsoft.com/azure/information-protection/plan-design/prepare#group-membership-caching-by-azure-information-protection)には、数時間かかることがあります。  
 - ラベル構成に直接外部ユーザーのアカウントを追加します。 組織 (例: Fabrikam.com) のすべてのユーザー、Microsoft 365 グループ (組織内の財務グループなど)、またはユーザーを追加できます。 たとえば、規制機関の外部チームを機密度ラベルのアクセス許可に追加することができます。

## <a name="see-also"></a>関連項目

[選挙運動、非営利組織、およびその他のアジャイル組織のための Microsoft Security ガイダンス](/security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[クラウド導入およびハイブリッド ソリューション](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
