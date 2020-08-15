---
title: 保持ラベルを使用してレコードを宣言する
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 保持ラベルを使用してレコードを宣言する。
ms.openlocfilehash: c8024cf08be2259ffa8b6747bebf4943e11e4d60
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695264"
---
# <a name="declare-records-by-using-retention-labels"></a>保持ラベルを使用してレコードを宣言する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

[保持ラベル](retention.md#retention-labels)を使用して、コンテンツをレコードとしてマークします。 それらの保持ラベルを発行してユーザーや管理者が手動でコンテンツに適用できるようにするか、レコードとしてマークするコンテンツにそれらのラベルを自動的に適用することができます。

## <a name="configuring-retention-labels-to-declare-records"></a>保持ラベルを構成してレコードを宣言する

[保持ラベル](retention.md#retention-labels)を作成するときに、そのコンテンツをレコードとしてマークするオプションを選択します。

>[!NOTE] 
> Microsoft 365 コンプライアンスセンターで **情報 ガバナンス**から保持ラベルを作成または構成する場合、コンテンツをレコードとしてマークするオプションは利用できません。 代わりに **レコード管理**を使用する必要があります。

1. [Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com)で、**レコードの管理** \> **ファイル プラン**に移動します。 [**ファイルプラン**] ページで、[**ラベルの作成**] を選びます。

2. ウィザードの [**ラベルの設定**] ページで、コンテンツをレコードとして分類するオプションを選択します。
    
   ![[このラベルを使用して、コンテンツをレコードに分類する] チェックボックスをクリックします](../media/recordversioning6.png)

3. 必要に応じて、SharePoint や OneDrive のドキュメントと Exchange メールに保持ラベルを適用します。 手順については、以下を参照してください。
    
    - [アイテム保持ラベルを作成してアプリに適用する](create-apply-retention-labels.md)
    
    - [保持ラベルをコンテンツに自動的に適用する](apply-retention-labels-automatically.md)

## <a name="applying-the-configured-retention-label-to-content"></a>コンテンツに構成した保持ラベルを適用する

保持ラベルは、コンテンツをレコードとしてマークする場合、ユーザーが以下のようにアプリ内でそれを適用できるようになります。

- Exchange の場合、メールボックスへの書き込みアクセス権を持つすべてのユーザーは、これらのラベルを適用できます。 
- SharePoint および OneDrive の場合、既定のメンバー グループ (投稿アクセス許可レベル) のすべてのユーザーがこれらのラベルを適用できます。

保持ラベルを使用してレコードとしてマークされたドキュメントの例は、以下のとおりです。

![レコードとしてタグ付けされたドキュメントの詳細ウィンドウ](../media/recordversioning7.png)

## <a name="next-steps"></a>次の手順

レコードであるドキュメントを更新する必要がある場合は、「[レコードのバージョン管理を使用して SharePoint または OneDriveに保存されているレコードを更新する](record-versioning.md)」を参照してください。

レコードの廃棄の詳細については、「[コンテンツの廃棄](disposition.md)」 を参照してください。
