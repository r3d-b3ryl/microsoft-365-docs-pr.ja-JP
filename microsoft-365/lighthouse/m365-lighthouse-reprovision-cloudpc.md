---
title: Microsoft 365 LighthouseでWindows 365 クラウド PCを再プロビジョニングする
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolib
- M365-Lighthouse
search.appverid: MET150
description: Microsoft 365 Lighthouseを使用するマネージド サービス プロバイダー (MSP) の場合は、Microsoft 365 LighthouseでWindows 365 クラウド PCを再プロビジョニングする方法について説明します。
ms.openlocfilehash: c3ff7dac53798f26da212ac4790ba0cb1412c307
ms.sourcegitcommit: e624221597480295b799d56568c4f6f56d40b41d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2022
ms.locfileid: "65535886"
---
# <a name="reprovision-a-windows-365-cloud-pc-in-microsoft-365-lighthouse"></a>Microsoft 365 LighthouseでWindows 365 クラウド PCを再プロビジョニングする

Microsoft 365 Lighthouseは、プロビジョニング ポリシーを持つクラウド PC の再プロビジョニングをサポートします。 新しいユーザーのデバイスの再プロビジョニングが必要な場合や、デバイスが正常に動作していない場合があります。 再プロビジョニングがトリガーされると、クラウド PC は削除され、新しいクラウド PC として再作成されます。 すべてのユーザー データ、アプリケーション、カスタマイズなどが削除されます。

## <a name="before-you-begin"></a>はじめに

パートナー テナントのクラウド PC 管理者である必要があります。

## <a name="reprovision-a-windows-365-cloud-pc"></a>Windows 365 クラウド PCを再プロビジョニングする

1. Lighthouse の左側のナビゲーション ウィンドウで、**Windows 365** を選択します。

2. [ **すべてのクラウド PC** ] タブを選択します。

3. **[フィルター**] ドロップダウン リストから、ライセンスの種類を選択します。

4. フィルター処理された一覧から、デバイスを選択します。

5. デバイスの詳細ウィンドウで、[ **再プロビジョニング**] を選択します。

6. 確認ダイアログで、[ **再プロビジョニング**] を選択します。

> [!NOTE]
> クラウド PC の現在のユーザーはすぐにサインアウトされ、すべてのユーザー データが削除されます。

## <a name="check-the-device-action-status"></a>デバイス アクションの状態を確認する

1. Lighthouse の左側のナビゲーション ウィンドウで、**Windows 365** を選択します。

2. [ **すべてのクラウド PC** ] タブを選択します。

3. デバイスの一覧から、デバイスを選択します。

4. デバイスの詳細ウィンドウで、[ **デバイス アクションの状態** ] タブを選択します。

このタブには、アクションの種類、状態、タイムスタンプなど、このデバイスのキューに入っている現在のアクションが表示されます。

## <a name="related-content"></a>関連コンテンツ

[プロビジョニングの概要](/windows-365/enterprise/provisioning) (記事)\
[プロビジョニング ポリシーの編集](/windows-365/enterprise/edit-provisioning-policy) (記事)
