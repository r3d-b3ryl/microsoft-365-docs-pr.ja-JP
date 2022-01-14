---
title: Microsoft マネージド デスクトップ用に、印刷リソースを準備する
description: 印刷がスムーズに機能するための重要な手順
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: 9ba4775c817e78691ecd093d40ed7bd6d6908255
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2022
ms.locfileid: "62034480"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップ用に、印刷リソースを準備する

Microsoft Managed Desktop に登録する準備が整ったら、印刷要件を評価し、環境に適切なアプローチを決定する必要があります。 次の 3 つのオプションがあります。

- Microsoft ユニバーサル 印刷ソリューションを展開して、Microsoft Managed Desktop デバイスがプリンターを簡単に検出できます。 詳細については [、「What is Universal Print 」を参照してください](/universal-print/fundamentals/universal-print-whatis)。
- カスタム PowerShell スクリプトを使用してプリンターを直接展開します。 「ローカル プリンターのセットアップ [」セクションの手順に従](#set-up-local-printers) います。
- Microsoft 以外のクラウド印刷ソリューションを使用します。このソリューションは、Windows 10ドメインに参加しているデバイスとAzure Active Directoryします。 ソリューションは、Microsoft Managed Desktop のソフトウェア要件を満たす必要があります。 詳細については [、「Microsoft Managed Desktop アプリの要件」を参照してください](../service-description/mmd-app-requirements.md)。
 
すべての場合、プリンター ドライバーが Microsoft Update または Microsoft Store から利用できない場合は、それらを入手し、Microsoft Intune を使用して Microsoft マネージ デスクトップ デバイスに展開するためにパッケージ化する必要があります。 詳細については [、「Intune スタンドアロン - Win32 アプリ管理」を参照してください。](/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>ローカル プリンターのセットアップ

カスタム PowerShell スクリプトを使用してプリンターを展開し、印刷リソースを準備した場合は、次の手順に従って共有プリンターを展開します。

1. Microsoft Managed Desktop ポータルに移動します。
2. 次の詳細を提供 *して、管理* ポータルの [サポート >サポート要求] セクションで、プリンターの展開というラベルの付いた要求を送信します。
    - Microsoft Managed Desktop デバイスに展開する必要がある共有プリンターの場所へのすべての UNC パス
    - これらの共有プリンターへのアクセスを必要とするユーザー グループ
3. 管理ポータルを使用して、要求がいつ完了したのかお知らせします。 最初は、テスト展開グループ内のデバイスにのみ構成を展開します。
4. 構成が期待通り動作するかどうかをテストして確認する必要があります。 サポート要求の [ **ディスカッション]** タブを使用して返信し、テストが完了したらお知らせします。
5. その後、構成を他の展開グループに展開します。

## <a name="steps-to-get-ready"></a>準備の手順

1. [Microsoft マネージド デスクトップの前提条件](prerequisites.md)を確認します。
2. [準備状況の評価ツール](readiness-assessment-tool.md)を実行します。
1. [ポータル サイト](../get-started/company-portal.md)を購入します。
1. [ゲスト アカウントの前提条件](guest-accounts.md)を確認します。
1. [ネットワーク構成](network.md)をチェックします。
1. [証明書とネットワーク プロファイル](certs-wifi-lan.md)を準備します。
1. [データへのユーザー アクセスを準備します](authentication.md)。
1. [アプリを準備します](apps.md)。
1. [マップ済みドライブを準備します](mapped-drives.md)。
1. 印刷リソースを準備する (この記事)。
1. [デバイス名](address-device-names.md)をアドレス指定します。
