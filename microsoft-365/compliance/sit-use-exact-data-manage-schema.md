---
title: 正確なデータ一致スキーマを管理する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 正確なデータ一致スキーマを編集または削除する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fb8a9d014bb4654ce39b0bb6312f8b20cd6d781e
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66629147"
---
# <a name="manage-your-exact-data-match-schema"></a>正確なデータ一致スキーマを管理する

## <a name="editing-the-schema-for-edm-based-classification-manually"></a>EDM ベースの分類のスキーマを手動で編集する

EDM ベースの分類に使用されるフィールドの変更など、 **edm.xml** ファイルなど、EDM スキーマに変更を加える場合は、次の手順に従います。

> [!TIP]
> 構成 **可能な一致** を利用するように、EDM スキーマと機密情報テーブルのソース ファイルを変更できます。 構成されている場合、EDM はアイテムを評価するときに、大文字と小文字の違いと一部の区切り文字を無視します。 これにより、xml スキーマと機密データ ファイルの定義が容易になります。 詳しくは、「 [caseInsensitive フィールドと ignoredDelimiters フィールドの使用](sit-get-started-exact-data-match-create-schema.md#using-the-caseinsensitive-and-ignoreddelimiters-fields)」をご覧ください。

1. **edm.xml** ファイルを編集します (これは、[完全一致ベースの機密情報の種類のスキーマの作成](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types)に関する記事で説明されているファイルです。

2. [セキュリティ/コンプライアンス PowerShell に接続します](/powershell/exchange/connect-to-scc-powershell)。

3. データベース スキーマを更新するには、次のコマンドを実行します。

      ```powershell
      Set-DlpEdmSchema -FileData ([System.IO.File]::ReadAllBytes('.\\edm.xml')) -Confirm:$true
      ```

      次のように、確認を求められます。

      > 確認
      >
      > この操作を実行しますか?
      >
      > データストア ' patientrecords ' の EDM スキーマが更新されます。
      >
      > \[Y\] Yes \[A\] すべて Yes \[N\] No \[L\] すべて No \[?\] ヘルプ (規定値は "Y"):

      > [!TIP]
      > 変更を確認せずに行う場合は、手順 3 で使用 `-Confirm:$true` しないでください。

      > [!NOTE]
      > 追加機能を使用して EDMSchema を更新するには、10 から 60 分かかることがあります。 追加機能を使用する手順を実行する前に、更新プログラムを完了する必要があります。

## <a name="removing-the-schema-for-edm-based-classification-manually"></a>EDM ベースの分類のスキーマを手動で削除する

EDM ベースの分類に使用しているスキーマを削除する場合は、次の手順に従います。

1. [セキュリティ/コンプライアンス PowerShell に接続します](/powershell/exchange/connect-to-scc-powershell)。

2. 次のコマンドを実行し、"患者レコード" のデータ ストア名を削除する名前に置き換えます (例として patientrecords ストアを使用)。

      ```powershell
      Remove-DlpEdmSchema -Identity 'patientrecords'
      ```

      次のように確認を求められます。

      > 確認
      >
      > この操作を実行しますか?
      >
      > データストア ' patientrecords ' の EDM スキーマが削除されます。
      >
      > \[Y\] Yes \[A\] すべて Yes \[N\] No \[L\] すべて No \[?\] ヘルプ (規定値は "Y"):

      > [!TIP]
      > 変更を確認せずに行う場合は、手順 2 で使用 `-Confirm:$true` しないでください。

### <a name="edit-or-delete-the-edm-schema-with-the-wizard"></a>ウィザードを使用して EDM スキーマを編集または削除する

1. **コンプライアンス センター** \> **のデータ分類** \> **の完全一致を開きます**。

2. **EDM スキーマを選択します**。

3. 編集する EDM SIT を選択します。

4. ポップアップから **[EDM スキーマの編集]** または **[EDM スキーマの削除** ] を選択します。

> [!IMPORTANT]
> スキーマを削除し、それが既に EDM の機密情報の種類に関連付けられている場合は、まずEDM の機密情報の種類を削除し、その後、スキーマを削除できます。
