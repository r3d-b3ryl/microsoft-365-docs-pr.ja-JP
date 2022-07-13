---
title: Microsoft Defender for Businessでファイアウォール ポリシーのカスタム ルールを管理する
description: カスタム ルールは、ファイアウォール ポリシーに例外を提供します。 カスタム ルールを使用して、Defender for Business で特定の接続をブロックまたは許可できます。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: cb584d01f2ca135a25ef715fe7152c1fe33ce0f3
ms.sourcegitcommit: fa90763559239c4c46c5e848939126763879d8e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2022
ms.locfileid: "66772711"
---
# <a name="manage-your-custom-rules-for-firewall-policies-in-microsoft-defender-for-business"></a>Microsoft Defender for Businessでファイアウォール ポリシーのカスタム ルールを管理する

Defender for Business には、不要なネットワーク トラフィックからデバイスを保護するのに役立つファイアウォール ポリシーが含まれています。 カスタム規則を使用して、ファイアウォール ポリシーの例外を定義できます。 つまり、カスタム ルールを使用して、特定の接続をブロックまたは許可できます。

ファイアウォール ポリシーと設定の詳細については、「 [Defender for Business のファイアウォール」を](mdb-firewall.md)参照してください。

**この記事では、次の方法について説明します**。

- [ファイアウォール ポリシーのカスタム規則を作成する](#create-a-custom-rule-for-a-firewall-policy)
- [ファイアウォール ポリシーのカスタム規則を編集する](#edit-a-custom-rule-for-a-firewall-policy)
- [カスタム ルールを削除する](#delete-a-custom-rule)


## <a name="create-a-custom-rule-for-a-firewall-policy"></a>ファイアウォール ポリシーのカスタム規則を作成する

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. **Endpoints デバイスの** > **構成** に移動し、ポリシーの一覧を確認します。

3. [ **ファイアウォール** ] セクションで、既存のポリシーを選択するか、新しいポリシーを追加します。

4. [ **構成設定]** ステップで、設定を確認します。 **ドメイン ネットワーク**、**パブリック** ネットワーク、プライベート ネットワークに必要な変更を加 **えます**。

5. カスタム ルールを作成するには、次の手順に従います。 

   1. [ **カスタム ルール**] で、[ **+ ルールの追加]** を選択します。 (最大 150 個のカスタム ルールを使用できます)。
   2. [ **新しいルールの作成** ] ポップアップで、ルールの名前と説明を指定します。
   3. プロファイルを選択します。 (オプションには **、ドメイン ネットワーク**、 **パブリック ネットワーク**、または **プライベート ネットワーク** が含まれます)。
   4. [ **リモート アドレスの種類** ] ボックスの一覧で、 **IP** または **アプリケーション ファイルのパス** を選択します。
   5. [ **値** ] ボックスで、適切な値を指定します。 手順 6d で選択した内容に応じて、IP アドレス、IP アドレス範囲、またはアプリケーション ファイル パスを指定できます。 ( [ファイアウォールの設定を](mdb-firewall.md)参照してください)。)
   6. [ **新しいルールの作成** ] ポップアップで、[ **ルールの作成**] を選択します。 

6. [ **構成設定** ] 画面で、[ **次へ**] を選択します。

7. [ **ポリシーの確認** ] 画面で、ファイアウォール ポリシー設定に加えられた変更を確認します。 必要な変更を加え、[ **ポリシーの作成**] を選択します。

## <a name="edit-a-custom-rule-for-a-firewall-policy"></a>ファイアウォール ポリシーのカスタム規則を編集する

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. **Endpoints デバイスの** > **構成** に移動し、ポリシーの一覧を確認します。

3. [ **ファイアウォール** ] セクションで、既存のポリシーを選択するか、新しいポリシーを追加します。

4. [ **カスタム ルール**] で、ルールの一覧を確認します。

5. ルールを選択し、[ **編集]** を選択します。 ポップアップが開きます。

6. カスタム ルールを編集するには、次の手順に従います。

   1. **[ルールの編集]** ポップアップで、ルールの名前と説明を確認して編集します。
   2. ルールのプロファイルを確認し、必要に応じて編集します。 (オプションには **、ドメイン ネットワーク**、 **パブリック ネットワーク**、または **プライベート ネットワーク** が含まれます)。
   3. [ **リモート アドレスの種類** ] ボックスの一覧で、 **IP** または **アプリケーション ファイルのパス** を選択します。
   4. [ **値** ] ボックスで、適切な値を指定します。 手順 6c で選択した内容に応じて、IP アドレス、IP アドレス範囲、またはアプリケーション ファイル パスを指定できます。 ( [ファイアウォールの設定を](mdb-firewall.md)参照してください)。)
   5. **ルールをアクティブにするには、[ルールを有効にする]** を **[オン]** に設定します。 または、ルールを無効にするには、スイッチを **[オフ]** に設定します。
   6. **[ルールの編集]** ポップアップで、[**ルールの更新**] を選択します。 

7. [ **構成設定** ] 画面で、[ **次へ**] を選択します。

8. [ **ポリシーの確認** ] 画面で、ファイアウォール ポリシー設定に加えられた変更を確認します。 必要な変更を加え、[ **ポリシーの作成**] を選択します。

## <a name="delete-a-custom-rule"></a>カスタム ルールを削除する

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. **Endpoints デバイスの** > **構成** に移動し、ポリシーの一覧を確認します。

3. [ **ファイアウォール** ] セクションで、既存のポリシーを選択するか、新しいポリシーを追加します。

4. [ **カスタム ルール**] で、ルールの一覧を確認します。

5. ルールを選択し、[削除] を選択 **します**。 ポップアップが開きます。

6. 確認画面で、[削除] を選択 **します**。 

## <a name="next-steps"></a>次の手順

- [Defender for Business でインシデントを表示および管理する](mdb-view-manage-incidents.md)
- [Defender for Business の脅威に対応し、軽減する](mdb-respond-mitigate-threats.md)
- [アクション センターで修復アクションを確認する](mdb-review-remediation-actions.md)