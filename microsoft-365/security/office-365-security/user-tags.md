---
title: Microsoft Defender for Office 365 のユーザータグ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 管理者は、Office 365 プラン2の Microsoft Defender でユーザータグを使用して、ユーザーの特定のグループを特定する方法について説明します。 タグフィルターは、Microsoft Defender for Office 365 のアラート、レポート、および調査に対して利用でき、タグ付きユーザーをすばやく識別できます。
ms.openlocfilehash: 136de95addae7dcd48de2c6ac1f30ce67714817c
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2020
ms.locfileid: "49552021"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 のユーザータグ

> [!NOTE]
> ユーザータグ機能はプレビューでは、すべてのユーザーが利用できるわけではなく、変更される可能性があります。 リリーススケジュールの詳細については、 [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap)をご覧ください。

ユーザータグとは、 [office 365 の Microsoft Defender](office-365-atp.md)で特定のユーザーグループの識別子です。 ユーザータグには、次の2種類があります。

- **システムタグ**: 現時点では、 [優先度のアカウント](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) のみがシステムタグの種類です。
- **カスタムタグ**: これらのユーザータグは自分で作成します。

組織が Office 365 プラン 2 (サブスクリプションに含まれているか、またはアドオン) に対して Defender を使用している場合は、[優先度のアカウント] タグを使用するだけでなく、カスタムユーザータグを作成することもできます。

システムタグまたはカスタムタグをユーザーに適用した後、それらのタグを警告、レポート、および調査のフィルターとして使用できます。

- [セキュリティ & コンプライアンスセンターのアラート](alerts.md)
- [脅威エクスプローラーとリアルタイム検出](threat-explorer.md)
- [脅威保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)
- [キャンペーン ビュー](campaigns.md)
- 優先度アカウントの場合は、Exchange 管理センター (EAC) の [ [優先度の高いアカウントの電子メールの問題] レポート](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) を使用できます。

この記事では、セキュリティ & コンプライアンスセンターでユーザータグを構成する方法について説明します。 セキュリティ & コンプライアンスセンターでユーザータグを管理するためのコマンドレットはありません。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 [ **ユーザータグ** ] ページに直接移動するには、を開き <https://protection.office.com/userTags> ます。

- **カスタムユーザータグ** を作成、変更、または削除するには、セキュリティ & コンプライアンスセンターの [**組織の管理**] または [**セキュリティ管理者**] 役割グループのメンバーである必要があります。 詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

- 優先アカウント (システムタグ) を構成するには、 [全体管理](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) 者または [Exchange 管理者](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)である必要があります。

  また、Microsoft 365 管理センターで優先アカウントを管理および監視することもできます。 手順については、「 [優先度のアカウントの管理と監視](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)」を参照してください。

## <a name="use-the-security-center-to-create-user-tags"></a>セキュリティセンターを使用してユーザータグを作成する

1. セキュリティセンターで、[ **脅威管理** \> **ユーザータグ**] に移動します。

2. 表示される [ **ユーザータグ** ] ページで、[ **タグの作成**] をクリックします。

3. **タグ作成** ウィザードが新しいフライアウトで開きます。[**タグの定義**] ページで、次の設定を構成します。
   - [**名前**]: タグのわかりやすい一意の名前を入力します。 これは、表示され、使用される値です。
   - **説明**: タグの説明 (省略可能) を入力します。

   完了したら、**[次へ]** をクリックします。

4. [ **ユーザーの割り当て** ] ページで、次のいずれかの手順を実行します。

   - [ **ユーザーの追加**] をクリックします。 スライドが表示されたら、次のいずれかの手順を実行して、個々のユーザーまたはグループを追加します。
     - ボックスをクリックしてリストをスクロールし、ユーザーまたはグループを選択します。
     - ボックス内をクリックして入力を開始し、リストにフィルターを適用してユーザーまたはグループを選択します。
     - その他の値を追加するには、ボックスの空の領域をクリックします。
     - ボックスから個々のエントリを削除するに **Remove** は、 ![ ](../../media/scc-remove-icon.png) ボックスで、ユーザーまたはグループの [削除] アイコンをクリックします。
     - ボックスの一覧から既存のエントリを削除するには **、[削除**] アイコンをクリックしてエントリを削除し ![ ](../../media/scc-remove-icon.png) ます。

     完了したら、[ **追加**] をクリックします。

   - [ **インポート** ] をクリックして、ユーザーまたはグループの電子メールアドレスが含まれるテキストファイルを選択します。 テキストファイルには、行ごとに1つのエントリが含まれていることを確認してください。

   完了したら、**[次へ]** をクリックします。

5. [ **タグの確認** ] ページで、設定を確認します。 特定のセクションの [ **編集** ] をクリックして、変更を加えることができます。

   完了したら、[ **送信**] をクリックします。

## <a name="use-the-security-center-to-view-user-tags"></a>セキュリティセンターを使用してユーザータグを表示する

1. セキュリティセンターで、[ **脅威管理** \> **ユーザータグ**] に移動します。

2. 表示される [ **ユーザータグ** ] ページで、表示するユーザータグを選択します (チェックボックスをクリックしないでください)。

3. 読み取り専用の詳細が表示されたら、設定を確認します。

   完了したら、**[閉じる]** をクリックします。

## <a name="use-the-security-center-to-modify-user-tags"></a>セキュリティセンターを使用してユーザータグを変更する

1. セキュリティセンターで、[ **脅威管理** \> **ユーザータグ**] に移動します。

2. 表示される [ **user tags** ] ページで、表示するユーザータグを選択し、[タグの **編集**] をクリックします。

3. ポリシーウィザードは、 **編集タグ** で開きます。[ **次へ** ] をクリックして、設定を確認および変更します。

   完了したら、[ **送信**] をクリックします。

## <a name="use-the-security-center-to-remove-user-tags"></a>セキュリティセンターを使用してユーザータグを削除する

**注**: 組み込みの **優先度の account** タグを削除することはできません。

1. セキュリティセンターで、[ **脅威管理** \> **ユーザータグ**] に移動します。

2. 表示される [ **ユーザータグ** ] ページで、削除するユーザータグを選択し、[ **タグの削除**] をクリックしてから、[ **はい、削除** ] を選択します。この警告が表示されます。
