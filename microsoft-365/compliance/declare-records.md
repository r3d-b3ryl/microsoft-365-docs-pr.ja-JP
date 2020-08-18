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
ms.openlocfilehash: d637817e8d1bcc8c72bfe011dfd288ac4e2d0298
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778517"
---
# <a name="declare-records-by-using-retention-labels"></a>保持ラベルを使用してレコードを宣言する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

アイテムをレコードとして宣言するには、コンテンツをレコードとしてマークする[保持ラベル](retention.md#retention-labels)を使用します。 それらの保持ラベルを発行してユーザーや管理者が手動でコンテンツに適用できるようにするか、レコードとしてマークするコンテンツにそれらのラベルを自動的に適用することができます。

## <a name="configuring-retention-labels-to-declare-records"></a>保持ラベルを構成してレコードを宣言する

保持ラベルを作成または構成するときに、そのコンテンツをレコードとしてマークするオプションを選択します。

>[!NOTE] 
> Microsoft 365 コンプライアンスセンターで **情報 ガバナンス**から保持ラベルを作成または構成する場合、コンテンツをレコードとしてマークするオプションは利用できません。 代わりに **レコード管理**を使用する必要があります。

コンテンツをレコードとしてマークする新しい保持ラベルを作成するには、次の操作を行います。

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

レコード管理でサポートされているシナリオの一覧については、「[レコード管理の一般的なシナリオ](get-started-with-records-management.md#common-scenarios-for-records-management)」を参照してください。
