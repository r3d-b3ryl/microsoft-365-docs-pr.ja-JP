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
description: 完全なデータ一致スキーマを編集または削除する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8e06cb25db0a8c616b5b692a423d9827e8918dc9
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2022
ms.locfileid: "63525195"
---
# <a name="manage-your-exact-data-match-schema"></a>正確なデータ一致スキーマを管理する

## <a name="editing-the-schema-for-edm-based-classification-manually"></a>EDM ベースの分類のスキーマを手動で編集する

EDM スキーマ ( **edm.xml** ファイルなど) を変更する場合 (EDM ベースの分類に使用するフィールドの変更など)、次の手順を実行します。

> [!TIP]
> EDM スキーマと機密情報テーブル ソース ファイルを変更して、構成可能な一致を **利用できます**。 構成されている場合、EDM はアイテムを評価するときに、大文字と小文字の違いと一部の区切り文字を無視します。 これにより、xml スキーマと機密データ ファイルの定義が容易になります。 詳細については、「 [CaseInsensitive フィールドと ignoredDelimiters フィールドを使用する」を参照してください](sit-get-started-exact-data-match-create-schema.md#using-the-caseinsensitive-and-ignoreddelimiters-fields)。

1. ファイルを **edm.xml** します (これは、「完全なデータ一致ベースの機密情報の種類のスキーマを作成する」で [説明されているファイルです](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types))。

2. [セキュリティ/コンプライアンス センターの PowerShell に接続する](/powershell/exchange/connect-to-scc-powershell)。

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
      > 確認なしで変更を行う場合は `-Confirm:$true` 、手順 3 では使用しません。

      > [!NOTE]
      > 追加機能を使用して EDMSchema を更新するには、10 から 60 分かかることがあります。 追加機能を使用する手順を実行する前に、更新プログラムを完了する必要があります。

## <a name="removing-the-schema-for-edm-based-classification-manually"></a>EDM ベースの分類のスキーマを手動で削除する

EDM ベースの分類に使用しているスキーマを削除する場合は、次の手順を実行します。

1. [セキュリティ/コンプライアンス センターの PowerShell に接続する](/powershell/exchange/connect-to-scc-powershell)。

2. 次のコマンドを実行し、"患者レコード" のデータ ストア名を削除するデータ ストア名に置き換えてください (例として、patientrecords ストアを使用します)。

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
      > 確認なしで変更を行う場合は `-Confirm:$true` 、手順 2 では使用しません。

### <a name="edit-or-delete-the-edm-schema-with-the-wizard"></a>ウィザードを使用して EDM スキーマを編集または削除する

1. Open **Compliance center** \> **Data classification** \> **Exact data matches**.

2. **[EDM スキーマ] を選択します**。

3. 編集する EDM SIT を選択します。

4. [ **EDM スキーマの編集] または** **[EDM スキーマをフライアウト** から削除] を選択します。

> [!IMPORTANT]
> スキーマを削除し、それが既に EDM の機密情報の種類に関連付けられている場合は、まずEDM の機密情報の種類を削除し、その後、スキーマを削除できます。
