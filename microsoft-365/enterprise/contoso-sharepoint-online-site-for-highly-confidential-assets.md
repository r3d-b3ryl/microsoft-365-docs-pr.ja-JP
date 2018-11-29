---
title: コントソ株式会社のデジタル資産の機密性の高い SharePoint Online サイト
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/01/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom: Ent_Architecture
description: '概要: contoso 社が高度の SharePoint Online サイトを実装する方法の研究の間で簡単に共同作業のための規制対象のデータがチームです。'
ms.openlocfilehash: 697ddb27b56fd529e9c73b89d9f07b8731ad76c3
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869590"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a>コントソ株式会社のデジタル資産の機密性の高い SharePoint Online サイト

 **の概要:** Contoso 社の研究チームの間で簡単に共同作業のための規制の厳しいデータを SharePoint Online サイトの実装方法です。
  
Contoso 社の最も貴重な資産はある知的財産が企業秘密は、独自の製造技術などの形で、設計、開発中の製品仕様サーバー 2016 の SharePoint サイト上のファイルとして保存された元のデジタル形式では、これらの資産です。Contoso 社では、Microsoft 365 エンタープライズを展開するときパリ、モスクワ、ニューヨーク、北京、バンガロールに研究チーム間で、設置型のデジタル資産を簡単にアクセスしより多くのコラボレーションのクラウドに移行するつもりでした。 
  
ただし、その機密性のためこれらのファイルへのアクセスを必要があります。

- 表示または SharePoint 管理者によってのみ管理サイトの継続的なアクセス許可を使用して、変更を許可されているユーザーのセットに制限されています。 
- データ損失防止 (DLP) ユーザーがサイトの外部に配布することを防ぐために保護されています。
- 暗号化され保護されているアクセスは、サイトの外部ユーザーに配布されている場合でも、その内容にアクセスする権限のないユーザーを防ぐためにリストを制御します。

Contoso 社のセキュリティと SharePoint の管理者の IT 部門は[の SharePoint Online サイト規制の厳しいデータ](teams-sharepoint-online-sites-highly-regulated-data.md)を使用することにしました。
  
Contoso 社では、次の手順を使用して作成し、研究チームの SharePoint Online のチーム サイトをセキュリティで保護されました。

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a>手順 1: レビューし、研究チームのグループのメンバーを確認

Contoso の IT 管理者は、研究チームのセキュリティ グループのセットのレビューを実行します。これらの削除人が、研究者または研究資産へのアクセスを必要はありませんでした。 

これらの新しいセキュリティ グループを作成します。

- **研究管理者** 一連のアクセス許可を変更する機能を含め、サイトに対するフル コントロールを持つ SharePoint 管理者です。
- **研究メンバー** 研究チームが世界中のセキュリティ グループのセット。
- **視聴者の調査** サイトに、アセットを表示することができる研究組織の経営幹部などの管理のユーザーのセットです。

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a>手順 2: SharePoint Online の分離のチーム サイトを作成します。 

Contoso 社の SharePoint 管理者が最初に作成された新しいチーム サイトでは、**研究**という名前です。それらをし、構成します。

- **研究 Admins**セキュリティ グループをメンバーとしての研究の所有者 SharePoint グループを使用するのにはフル コントロール アクセス許可のレベル
- 編集アクセス許可のレベル、メンバーとして、**研究メンバー**のセキュリティ グループを持っている研究のメンバー SharePoint グループを使用するには
- **リサーチ ビューアー**のセキュリティ グループをメンバーとして、研究の訪問者の SharePoint グループを使用するのには読み取りアクセス許可のレベル

結果の SharePoint アクセス許可レベル、SharePoint グループ、およびそのメンバーを次に示します。

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

次に、これらのサイトの追加の制限を構成します。

構成の詳細については、[分離のオンラインの SharePoint チーム サイトの展開](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site)を参照してください。

## <a name="step-3-configured-the-site-for-a-restrictive-office-365-label-dlp-policy"></a>手順 3: 制限された Office 365 ラベル DLP ポリシーについては、サイトの構成

まず、Contoso の管理者では、**リサーチ**サイトに**機密性の高い**Office 365 のラベルが適用されます。

新しいを作成する次に、Office 365 の DLP ポリシーという名前の**研究**。

- **機密性の高い**Office 365 のラベルを使用します。 
- **リサーチ**サイトに適用されます。
- ドキュメントを共有できないようにします。

構成の詳細については、 [Office 365 のラベルと DLP を SharePoint Online を保護するためのファイル](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)を参照してください。

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a>ステップ 4: サイトの情報保護の Azure サブ ラベルを作成します。

Azure の情報保護のサブの新しいラベルを作成した Contoso 管理者という名前のスコープ指定ポリシーの既定の**機密度の高い**ラベルの**研究**。

- 暗号化が必要です。
- **研究メンバー**のセキュリティ グループのメンバーが完全にアクセスをできます。
- **研究のあるユーザー**のセキュリティ グループのメンバーでの読み取りアクセスを許可するには。

次に、研究チームのメンバーのデバイスへの Azure の情報保護のクライアントが展開されました。

構成の詳細については、 [Azure の情報保護を保護するための SharePoint Online ファイル](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection)を参照してください。 

ここでは、機密性の高い資産の**リサーチ**サイトの結果として得られる構成です。

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a>手順 5: は、設置型の SharePoint の研究データを移行します。

Contoso の管理者は、施設内でのすべての調査**研究**の SharePoint Online サイトにフォルダーを設置型の SharePoint サーバーの 2016年サイト内のファイルを移動します。

## <a name="step-6-trained-their-users"></a>手順 6: ユーザーのトレーニング 

Contoso 社のセキュリティ スタッフには、必須のコースを使用してステップ実行での調査チームがトレーニングを受けた。

- 新しい**研究**SharePoint Online サイトとその既存のファイルにアクセスする方法です。
- サイトに新しいファイルを作成し、ローカルに保存された新しいファイルをアップロードする方法。
- DLP ポリシーが外部で共有されているファイルをブロックする方法のデモンストレーションです。
- Azure 情報保護クライアントを使用して、調査**研究**サブ ラベル ファイルにラベルを付ける方法です。
- 方法のデモ**研究**サブのラベルは、サイトからリークしている場合でもにファイルを保護します。

最終的な結果は、セキュリティで保護された環境、研究者がセキュリティで保護された環境で組織全体にわたる共同作業が可能です。 

**研究**サブのラベルを持つ研究文書がリーク**研究**サイトから、暗号化され、有効な資格情報の**リサーチ メンバー**および**研究のあるユーザー**のセキュリティ グループのメンバーだけにアクセスがあります。

## <a name="next-step"></a>次の手順

組織に Microsoft 365 Enterprise を[展開](deploy-microsoft-365-enterprise.md)します。

