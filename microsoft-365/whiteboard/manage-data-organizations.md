---
title: Microsoft Whiteboard のデータを管理する
ms.author: chucked
author: chuckedmonson
manager: alexfaulkner
ms.reviewer: ''
audience: admin
ms.topic: article
ms.custom: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection: ''
ms.localizationpriority: medium
description: Azure とOneDrive for Businessでの Microsoft Whiteboard のデータリテンション期間について説明します。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2537750a43b10617251ee1da670f6ebd78e5ce82
ms.sourcegitcommit: bc35c7826e3403f259725ac72cca5bafd36aa56a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2022
ms.locfileid: "66553863"
---
# <a name="manage-data-for-microsoft-whiteboard"></a>Microsoft Whiteboard のデータを管理する

ホワイトボードコンテンツは、Azure とOneDrive for Businessの両方に格納されます。 新しいホワイトボードはOneDrive for Businessに格納されます。唯一の例外は、Surface Hub から開始されたホワイトボードが Azure に格納されます (今後OneDrive for Businessに移動されます)。 詳細については、「 [ホワイトボードでの共有の管理](manage-sharing-organizations.md)」を参照してください。

## <a name="azure-storage-overview"></a>Azure Storage の概要

ホワイトボードは現在、Azure にコンテンツを安全に格納しています。 データは、国と、Whiteboard がそれらの場所に新しいコンテンツを格納するように切り替えた時期に応じて、異なる場所に格納される場合があります。 新しいデータが作成される場所を確認するには、「 [Microsoft 365 顧客データの保存場所」を参照してください](/microsoft-365/enterprise/o365-data-locations)。 

Azure のコンテンツでは、データ損失防止 (DLP)、電子情報開示、アイテム保持ポリシー、および同様の機能はサポートされていません。 コンテンツは [Whiteboard PowerShell コマンドレット](/powershell/module/whiteboard/)を使用して管理でき、時間の経過と共に、このコンテンツをOneDrive for Businessに移行するか削除する必要があります。

### <a name="if-a-user-account-is-deleted-in-azure"></a>Azure でユーザー アカウントが削除された場合

Azure でユーザーのアカウントが削除されたときにホワイトボードを保存する方法を変更しています。 変更前は、ユーザーのアカウントが削除されたとき、ユーザーが所有していたホワイトボードも削除されましたが、他のユーザーと共有されていたホワイトボードは削除されませんでした。

>[!NOTE]
> OneDrive for Businessに格納されているホワイトボードは、OneDrive for Businessの他のコンテンツと同様に処理されます。 詳細については、「 [削除されたユーザーの OneDrive リテンション期間を設定する」を参照してください](/onedrive/set-retention)。

**2022 年 6 月 1** 日の時点で、Azure でのホワイトボードの動作が変更されました。 他のユーザーと共有されているホワイトボードはすべて削除されます。

削除されたユーザーのホワイトボードを保持する場合は、アカウントを削除する *前に* 所有権を譲渡できます。 1 つのホワイトボードまたはすべてのホワイトボードを別のユーザーに転送できます。 

- [すべてのホワイトボードを転送](/powershell/module/whiteboard/invoke-transferallwhiteboards)するには、次の手順に従います。

- ユーザー アカウントを削除する方法の詳細については、「 [組織からユーザーを削除する](/microsoft-365/admin/add-users/delete-a-user)」を参照してください。

削除プロセスまたはスクリプトがこの変更を処理することを確認します。 ホワイトボードを削除しても問題ない場合は、アクションは必要ありません。 

## <a name="onedrive-for-business-storage-overview"></a>OneDrive for Business ストレージの概要

ホワイトボードは、ホワイトボードを起動するユーザーのOneDrive for Business フォルダーに作成されます (SharePoint はまだサポートされていません)。 このプロセスは、スタンドアロンのホワイトボード アプリケーション、および Microsoft Teams の会議、チャット、チャネルで作成されたすべてのホワイトボードに適用されます。 唯一の例外は、Surface Hub から開始されたホワイトボードが Azure に格納されます (今後、OneDrive for Businessに移動されます)。

OneDrive for Businessプロビジョニングされていないユーザーは、この変更が実装されると、新しいホワイトボードを作成できなくなります。 ただし、以前に作成したボードは編集できます。 また、OneDrive for Businessを持つ他のユーザーが共有しているホワイトボードで共同作業を行うこともできます。

平均的なホワイトボードのサイズは 50 KB から 1 MB で、OneDrive for Business コンテンツが存在する場所であればどこでも配置できます。 テナントのデータが格納されている場所を確認するには、「 [Microsoft 365 顧客データの保存場所](/microsoft-365/enterprise/o365-data-locations)」を参照してください。 次に、OneDrive for Businessの場所を確認します。

### <a name="controls-for-onedrive-for-business-storage"></a>OneDrive for Businessストレージのコントロール 

既存のOneDrive for Business コントロールを使用してホワイトボード データを管理できます。 詳細については、 [企業向けの OneDrive ガイドを参照してください](/onedrive/plan-onedrive-enterprise)。

既存のOneDrive for Business ツールを使用して、一般データ保護規則 (GDPR) のデータ主体要求 (DSR) を満たすことができます。 以前のすべての変更がファイルから確実に削除されるようにするには、ファイル全体を削除する必要があります。

ホワイトボード ファイルは、OneDrive for Businessの他のコンテンツと同じ方法で移動できます。 ただし、共有リンクとアクセス許可が移動しない可能性があります。

現在サポートされているデータ コントロール:

- アイテム保持ポリシー
- Quota
- 訴訟ホールド
- DLP
- 基本的な電子情報開示 – .whiteboard ファイルは、作成者のOneDrive for Businessにファイルとして保存されます。 キーワードとファイルの種類の検索用にインデックスが作成されますが、プレビューまたは確認することはできません。 エクスポート時に、管理者はファイルをOneDrive for Businessにアップロードしてコンテンツを表示する必要があります。 今後、追加のサポートが予定されています。

今後のリリースで予定されているデータ コントロール:

- 秘密度ラベル
- 分析
- 追加の電子情報開示のサポート

## <a name="see-also"></a>関連項目

[ホワイトボードへのアクセスを管理する](manage-whiteboard-access-organizations.md)

[ホワイトボードの共有を管理する](manage-sharing-organizations.md)

[Windows にホワイトボードを展開する](deploy-on-windows-organizations.md)

