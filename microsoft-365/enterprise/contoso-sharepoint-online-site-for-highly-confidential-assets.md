---
title: Contoso Corporation の非常に機密性の高いデジタル資産向けの SharePoint サイト
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/18/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: '概要: 研究チーム間の共同作業を容易にするために、Contoso 社が非常に規制されたデータに対して SharePoint サイトを実装した方法を示します。'
ms.openlocfilehash: a1ffb336e85eb6eb850b53ed14adf947b56642cc
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068277"
---
# <a name="sharepoint-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a>Contoso Corporation の非常に機密性の高いデジタル資産向けの SharePoint サイト

Contoso 社の最も重要な資産は、独自の製造手法、開発中の製品の設計仕様など、企業秘密の形式での知的財産です。 これらのアセットはデジタル形式で、もともとは SharePoint Server 2016 サイトにファイルとして保存されていました。 Contoso 社では、Microsoft 365 Enterprise を展開したときに、オンプレミスのデジタルアセットをクラウドに移行して、パリ、モスクワ、ニューヨーク、北京、Bangalore の研究チーム間で簡単にアクセスできるようにしたいと考えています。 
  
ただし、機密性の高い性質上、これらのファイルへのアクセスは次のようにする必要があります。

- アクセスが許可されているユーザーのセットに制限されます。 
- データ損失防止 (DLP) ポリシーで保護され、ユーザーがサイト外に配布することを禁止します。
- アクセス許可を使用して保護され、権限のないユーザーがサイト外に配布されている場合でも、そのコンテンツにアクセスするのを防ぐことができます。

Contoso 社の IT 部門のセキュリティおよび SharePoint 管理者は、[高度な規制データ用に sharepoint サイト](teams-sharepoint-online-sites-highly-regulated-data.md)を使用することを決定しました。
  
Contoso 社は、これらの手順を使用して、調査チームのために SharePoint チームサイトを作成してセキュリティ保護しています。

## <a name="step-1-created-a-private-sharepoint-team-site"></a>手順 1: プライベート SharePoint チームサイトを作成する

SharePoint サイトへのアクセスを保護するために、Contoso 社は推奨される[sharepoint アクセスポリシー](sharepoint-file-access-policies.md)を構成しました。

次に Contoso IT 管理者は、パリ、モスクワ、ニューヨーク、北京、Bangalore オフィスの研究者のユーザーアカウントの一覧をコンパイルしていました。 

次に、Contoso IT 管理者は**Research**という名前の新しいプライベートチームサイトを作成し、その研究者のすべてのユーザーアカウントを追加しました。

その後、調査者がサイトへのアクセスを共有したり、研究者以外がサイトへのアクセスを要求したりできないように、サイトの追加のアクセス許可設定を構成しました。

## <a name="step-2-configured-the-site-for-a-restrictive-dlp-policy"></a>手順 2: 制限付き DLP ポリシー用にサイトを構成する

最初に、Contoso 管理者は、**リサーチ**サイトの Documents フォルダーに既存の**高機密**Office 365 保持ラベルを適用しました。

次に、 **Research**という名前の新しい OFFICE 365 DLP ポリシーを作成しました。

- 非常に**機密性の高い**Office 365 保持ラベルを使用します。 
- ユーザーが Contoso 外の**Research**サイトでデジタルアセットを共有しようとすると、ユーザーをブロックします。

構成の詳細については、「 [SharePoint ファイルを保持ラベルおよび DLP で保護](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)する」を参照してください。

## <a name="step-3-created-an-office-365-sensitivity-sublabel-for-the-site"></a>手順 3: サイト用の Office 365 機密 sublabel を作成する

Contoso 管理者は、次のような**高機密**ラベルの**研究チーム**という名前の新しい Office 365 機密 sublabel を作成しました。

- 暗号化が必要です。
- **リサーチ**Office 365 グループに対して共同編集者の権限を許可する
- **Research** Office 365 グループに適用されます。

以下は、非常に機密性の高い資産を対象とした**研究**チームサイトの構成結果です。

![非常に機密性の高い資産を検索するための研究チームサイトの構成結果。](../media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

**リサーチ**サイトのフォルダー内のファイルは、次の方法で保護されます。

- サイトのアクセス許可。 **Research** Office 365 グループのメンバーにのみアクセスを許可します。
- **リサーチ**DLP ポリシー。**高機密**保持ラベルと、ファイルを外部ユーザーと共有できないようにする設定を使用します。
- **研究サイトから**移動またはコピーされた場合に、ファイルと共に移動する暗号化とアクセス許可を持つ、**調査チーム**の感度 sublabel。

**Research サイトに**保存されているファイルの例として、 **research Teams**の感度 sublabel が割り当てられています。

![非常に機密性の高い資産を検索するための研究チームサイトの構成結果。](../media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config-example-file.png)


## <a name="step-4-migrated-the-on-premises-sharepoint-research-data"></a>手順 4: オンプレミスの SharePoint リサーチデータを移行する

Contoso admins は、オンプレミスの SharePoint Server 2016 サイト内のすべてのオンプレミスの研究ファイルを新しい**research** sharepoint サイト内のフォルダーに移動しました。

## <a name="step-5-trained-their-researchers"></a>手順 5: 自分の研究者をトレーニングする

Contoso のセキュリティスタッフは、 **Research** Office 365 グループのメンバーに、次の手順に従ってステップインした必須コースをトレーニングしています。

- 新しい**リサーチ**サイトとその既存のファイルにアクセスする方法について説明します。
- サイトに新しいファイルを作成し、ローカルに保存された新しいファイルをアップロードする方法。
- **リサーチ**DLP ポリシーによって、ファイルが外部で共有されることをブロックする方法のデモ。
- **リサーチ Teams**の感度 sublabel でファイルにラベルを付ける方法について説明します。
- サイトからリークが生じた場合でも、 **Research Teams**のサブラベルがファイルを保護する方法のデモ。

最終的には、研究情報が含まれるファイルのセキュリティで保護された環境で、研究者が Contoso を越えて共同作業を行うことのできる安全な環境が得られます。 

Research **Teams**を使用した research ドキュメントが**research**サイトを離れた場合、sublabel は暗号化され、有効なユーザーアカウントの資格情報を持つ**research** Office 365 グループのメンバーのみがアクセスできます。

## <a name="next-step"></a>次の手順

[展開](deploy-microsoft-365-enterprise.md)組織内の Microsoft 365 Enterprise。

## <a name="see-also"></a>関連項目

[Microsoft 365 生産性向上ライブラリ](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)
