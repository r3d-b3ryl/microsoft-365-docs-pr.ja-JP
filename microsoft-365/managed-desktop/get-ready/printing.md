---
title: Microsoft マネージド デスクトップ用に、印刷リソースを準備する
description: 印刷がスムーズに機能するための重要な手順
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 81de89a704c8ff8717439d83e70504ba2fe8e410
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60188915"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップ用に、印刷リソースを準備する

アプリケーションに登録する準備が整ったMicrosoft マネージド デスクトップ、印刷要件を評価し、環境に適切なアプローチを決定する必要があります。 次の 3 つのオプションがあります。

- Microsoft Universal Print ソリューションを展開して、デバイスからプリンター Microsoft マネージド デスクトップ簡単に見つけられます。 詳細については [、「What is Universal Print 」を参照してください](/universal-print/fundamentals/universal-print-whatis)。
- カスタム PowerShell スクリプトを使用してプリンターを直接展開します。 「ローカル プリンターのセットアップ [」セクションの手順に従](#set-up-local-printers) います。
- Microsoft 以外のクラウド印刷ソリューションを使用します。このソリューションは、Windows 10ドメインに参加しているデバイスとAzure Active Directoryします。 ソリューションは、ソフトウェア要件を満たす必要Microsoft マネージド デスクトップ。 詳細については、「アプリの要件[Microsoft マネージド デスクトップを参照してください](../service-description/mmd-app-requirements.md)。
 
すべての場合、プリンター ドライバーが Microsoft Update または Microsoft Store から利用できない場合は、それらを入手し、Microsoft Intune を使用して Microsoft マネージド デスクトップ デバイスに展開するためにパッケージ化する必要があります。 詳細については [、「Intune スタンドアロン - Win32 アプリ管理」を参照してください。](/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>ローカル プリンターのセットアップ

カスタム PowerShell スクリプトを使用してプリンターを展開し、印刷リソースを準備した場合は、次の手順に従って共有プリンターを展開します。

1. ポータルに移動Microsoft マネージド デスクトップします。
2. 次の詳細を提供 *して、管理* ポータルの [サポート >サポート要求] セクションで、プリンターの展開というラベルの付いた要求を送信します。
    - デバイスに展開する必要がある共有プリンターの場所へのすべての UNC パスMicrosoft マネージド デスクトップします。
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
