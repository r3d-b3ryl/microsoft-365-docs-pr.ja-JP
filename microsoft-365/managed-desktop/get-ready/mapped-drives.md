---
title: Microsoft マネージド デスクトップ用に、マップされたドライブを準備する
description: マップされたドライブ上のデータにユーザーがアクセスできる重要な手順
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: d8100323350b11cb2329d752892cd64b1bc764a0
ms.sourcegitcommit: d4797cfc15c732f1a7ef21e4f944e672a7170f9a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2022
ms.locfileid: "62444559"
---
# <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップ用に、マップされたドライブを準備する

多くのエンタープライズ環境では、マップされたドライブに関する従来の要件を満たして、ユーザーまたはチームがファイルを共有および保存したり、オンプレミス アプリケーションを共有したり保存したりできます。

Microsoft は、Microsoft Managed Desktop でマップされたドライブの使用をお勧めしません。 代わりに、次のようにファイル アクセス ソリューションを最新化することをお勧めします。
  
- 個々のユーザーが使用するマップされたドライブを、OneDrive for Business。
- チームがファイルを共有するために使用するマップされたドライブをオンラインにSharePointします。
- オンプレミスのファイル共有を使用するアプリケーションを最新化または置き換え、その要件を削除します。
  
これらのサービスを最新化すると、Microsoft Managed Desktop で最高のユーザー エクスペリエンスを提供できます。 Microsoft FastTrackサービスは、Microsoft Cloud Services を使用して環境を最新化する場合に役立ちます。 対象となるサービスとプランで、FastTrack対象かどうかを[確認できます](/fasttrack/m365-eligible-services-and-plans)。 次に、Microsoft Managed Desktop の準備のために直接連絡してください。 オンライン移行またはオンライン移行FastTrack OneDrive for Business詳細SharePoint、データ移行を[参照してください](/fasttrack/o365-data-migration)。

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Microsoft Managed Desktop 上のマップされたドライブ

一部の使用例でマップされたドライブを削除または置き換えできない場合は、Microsoft Managed Desktop 管理ポータルでサポート要求を送信して、Microsoft Managed Desktop ユーザーに展開する必要があります。

このような要求の場合は、サポート要求に次の詳細を入力する必要があります。

- Microsoft Managed Desktop デバイスにマップする必要があるファイル共有場所へのすべての UNC パス。
- これらのファイル共有場所へのアクセスを必要とするユーザー グループ。
- 割り当てる必要がある特定のドライブ文字 (必要な場合)。

次に例を示します。

| ドライブ文字 | UNC パス | ユーザー グループ |
|--------------|----------|------------|
| X:  | \\\server\share\Marketing | ContosoMarketing |

次の責任は完全にユーザーの責任です。

- ユーザーとグループがファイル共有の場所にアクセスするための適切なアクセス許可を持ち、維持する必要があります。
- オンプレミスのファイル サービスにアクセス可能です。

このようなファイル共有の要件は、できるだけ早く削除する必要があります。

**Microsoft Managed Desktop にマップされたドライブを展開するには、次の方法を実行します。**

マップされたドライブを避けず、サポート要求を提出する前に要件を慎重に確認してください。

1. [トラブルシューティング] [Microsoft エンドポイント マネージャー](https://endpoint.microsoft.com/)し、[トラブルシューティングとサポート **] を選択します**。
1. [ **Microsoft Managed Desktop] セクションで** 、[サービス要求 **] を選択します**。
1. "マップされたドライブの展開" というタイトルのサポート要求を送信し、必要なすべてのファイル共有の詳細を提供します。  
1. Microsoft Managed Desktop IT Operations は、要求が完了したら、サポート要求の更新プログラムを使用して助言します。 最初は、この構成はテスト展開グループ内のデバイスにのみ展開されます。  
1. Microsoft Managed Desktop IT Operations によって展開された構成が期待通り動作するかどうかをテストして確認する必要があります。
1. 同じサポート要求で、[ディスカッション] タブを使用して返信し、テストが完了したら Microsoft Managed Desktop IT Operations に通知します。  
1. その後、Microsoft Managed Desktop IT Operations チームが構成を他の展開グループに展開します。

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>Microsoft Managed Desktop の準備をする手順

1. [Microsoft マネージド デスクトップの前提条件](prerequisites.md)を確認します。
1. [準備状況の評価ツール](readiness-assessment-tool.md)を実行します。
1. [ポータル サイト](../get-started/company-portal.md)を購入します。
1. [ゲスト アカウントの前提条件](guest-accounts.md)を確認します。
1. [ネットワーク構成](network.md)をチェックします。
1. [証明書とネットワーク プロファイル](certs-wifi-lan.md)を準備します。
1. [データへのユーザー アクセスを準備します](authentication.md)。
1. [アプリを準備します](apps.md)。
1. マップされたドライブを準備する (この記事)。
1. [印刷リソースを準備します](printing.md)。
1. [デバイス名](address-device-names.md)をアドレス指定します。
