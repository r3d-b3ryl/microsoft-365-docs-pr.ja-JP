---
title: Google ファイルをビジネス向け Microsoft 365 に移行する
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: SharePoint Migration Manager を使用して、ビジネス向け Microsoft 365 に Google ファイルを移行する方法について説明します。
ms.openlocfilehash: 68b3a0455a2bf57e35308c428bf2b5de3e4b5983
ms.sourcegitcommit: e9692a40dfe1f8c2047699ae3301c114a01b0d3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2022
ms.locfileid: "66602118"
---
# <a name="migrate-google-files-to-microsoft-365-for-business-with-migration-manager"></a>Migration Manager を使用してビジネス向けに Google ファイルを Microsoft 365 に移行する

YouTube の [Microsoft 365 小規模ビジネス ヘルプ](https://go.microsoft.com/fwlink/?linkid=2197659) を確認してください。

## <a name="watch-migrate-google-files-to-microsoft-365-for-business"></a>ウォッチ: Google ファイルをビジネス向け Microsoft 365 に移行する

[YouTube チャンネル](https://go.microsoft.com/fwlink/?linkid=2198217)で、このビデオや他の動画を確認してください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWSx43?autoplay=false]

Google ワークスペースからビジネス向け Microsoft 365 に移行する場合は、Google ドライブからファイルを移行する必要があります。 SharePoint 移行マネージャーを使用して、個人用ドライブと共有ドライブからファイルを移動できます。 このビデオと必要な手順の概要は、これを行う方法の概要を示しています。 詳細については、「[移行マネージャーを使用して Google Workspace を Microsoft 365 に移行する](/sharepointmigration/mm-google-overview)」を参照してください。

> [!NOTE]
> Migration Manager はファイルのコピーを作成し、コピーを Microsoft 365 に移動します。 元のファイルは Google ドライブにも残ります。

## <a name="before-you-start"></a>始める前に

すべてのユーザーがビジネス向けに Microsoft 365 にサインインし、OneDrive for Businessを設定している必要があります。 これを行うには、 [office.com](https://office.com) に移動し、ビジネス資格情報として Microsoft 365 でサインインし、OneDrive を選択します。

## <a name="install-the-microsoft-365-migration-app"></a>Microsoft 365 移行アプリをインストールする

次の手順に従って、Google ワークスペース環境に Microsoft 365 移行アプリをインストールします。 
1. SharePoint 管理 センターで、[移行] を選択 **します**。
2. [ **移行** ] ページの **[Google ワークスペース** ] セクションで、[ **作業の開始**] を選択します。
3. **[Google ワークスペース コンテンツを Microsoft 365 に移行** する] ページで、[**Google ワークスペースに接続**] を選択します。
4. [ **インストールと承認**] を選択します。
5. **Google ワークスペース Marketplace** ページ **で、[サインイン**] を選択し、Google ワークスペース管理者の資格情報を入力します。
6. [ **ドメインのインストール] を選択します**。
7. **[続行]** を選択します。
8. チェック ボックスをオンにし、[ **許可**] を選択します。
9. インストールが完了したら、[完了] を選択 **します**。
10. **[移行アプリのインストール] ページに** 戻り、[**次へ**] を選択します。
11. [ **Google ワークスペースへのサインイン**] を選択し、Google ワークスペース管理者の資格情報を入力します。
12. **[完了]** を選択します。

## <a name="select-and-scan-your-drives"></a>ドライブを選択してスキャンする

Google 環境に Microsoft 365 移行アプリをインストールした後、移行するドライブを選択し、それらをスキャンして、Microsoft 365 に安全にコピーできることを確認できます。

1. [ **スキャン** ] タブで、Microsoft 365 にコピーする Google ドライブを選択します。
2. [**スキャン**] を選択します。 スキャンが完了すると、ドライブに **移行準備完了** のスキャン状態が表示されます。
3. [ **移行にコピー] を選択します**。

## <a name="start-the-migration"></a>移行を開始する

移行するドライブを選択してスキャンした後、次の手順に従って移行します。

1. [ **移行** ] タブで、移行するドライブの宛先パスを確認します。 必要に応じて編集します。
2. 移行するドライブを選択し、[ **移行**] を選択します。 
3. 移行が正常に完了すると、各ドライブに **移行の状態** が **[完了]** と表示されます。