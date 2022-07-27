---
title: Microsoft 365 LighthouseでWindows 365 Business Cloud PC アカウントの種類を変更する
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: katmartin
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Microsoft 365 Lighthouseを使用するマネージド サービス プロバイダー (MSP) の場合は、Windows 365 Business Cloud PC アカウントの種類を設定または変更する方法について説明します。
ms.openlocfilehash: 398f1fb73e94ccb6a5e599ad1414988bc99284f2
ms.sourcegitcommit: 13a1199fbfeb329da77ce87b2781d5cc77e4a201
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2022
ms.locfileid: "67037780"
---
# <a name="change-a-windows-365-business-cloud-pc-account-type-in-microsoft-365-lighthouse"></a>Microsoft 365 LighthouseでWindows 365 Business Cloud PC アカウントの種類を変更する

マネージド サービス プロバイダー (MSP) の技術者は、Business Cloud PC のアカウントの種類を設定したり、既存のアカウントの種類を変更したりできます。 次のアカウントの種類を使用できます。

- **標準ユーザー (推奨)** - Standard ユーザー アカウントには、Microsoft Store からのみソフトウェアをインストールするアクセス許可があります。

- **ローカル管理者** - ローカル管理者アカウントには、ソフトウェアをインストールし、オペレーティング システムの任意の部分に変更を加えるアクセス許可があります。 マルウェアは管理者のアクセス許可を使用してファイルを感染または破損する可能性があるため、必要な場合にのみこのアカウントの種類を選択します。

> [!NOTE]
> アカウントの種類は、Business ライセンスを持つクラウド PC に対してのみ設定または変更できます。 Enterprise ライセンスを使用してクラウド PC のアカウントの種類を変更することはできません。

## <a name="before-you-begin"></a>始める前に 

パートナー テナントのWindows 365管理者またはグローバル管理者である必要があります。

## <a name="set-or-change-a-windows-365-business-cloud-pc-account-type"></a>クラウド PC アカウントの種類Windows 365 Business設定または変更する

1.  Lighthouse の左側のナビゲーション ウィンドウで、**デバイス** > **Windows 365** を選択します。

2.  [ **すべてのクラウド PC** ] タブを選択します。

3.  色分けされた count 注釈バーを使用して、 **プロビジョニングされた** 状態のクラウド PC にドリルインします。

4.  [ **フィルター** ] ドロップダウン メニューから[ **ビジネス** ライセンスの種類] を選択すると、顧客テナント内の Business ライセンスを持つすべてのクラウド PC の一覧が表示されます。

5.  クラウド PC の一覧から、アカウントの種類を変更するクラウド PC を選択します。

6.  **[Cloud PC の詳細**] ウィンドウで、[**アカウントの種類の変更**] を選択します。

7.  [ **クラウド PC アカウントの種類の変更** ] ウィンドウで、Cloud PC のアカウントの種類を選択し、[保存] を選択 **します**。

## <a name="next-steps"></a>次の手順

更新プログラムが適用されたら、クラウド PC の割り当てられたユーザーが Cloud PC にサインインするか、デバイスを再起動する必要があります。 新しい変更がMicrosoft 365 Lighthouseに表示されるまで数分かかる場合があります。 クラウド PC 管理者は、クラウド PC をリモートで再起動することもできますが、ユーザーは保存されていないデータを失う可能性があります。

## <a name="related-content"></a>関連コンテンツ

[クラウド PC ロールベースのアクセス制御](/windows-365/enterprise/role-based-access) (記事)\
[Microsoft 365 LighthouseのWindows 365 (クラウド PC) ページの概要](m365-lighthouse-win365-page-overview.md) (記事)\
[Microsoft 365 LighthouseでWindows 365 クラウド PCを再プロビジョニングする](m365-lighthouse-reprovision-cloudpc.md) (記事)
