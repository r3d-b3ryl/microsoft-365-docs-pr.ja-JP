---
title: Microsoft マネージド デスクトップ用に、印刷リソースを準備する
description: 印刷がスムーズに機能するための重要な手順
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 480106eacbcc809007ff1aa45d776bb89beaf78cb7aaeefce41df33dfc000af9
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53869943"
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

1. 詳細については[、「前提条件」をMicrosoft マネージド デスクトップ。](prerequisites.md)
2. 準備 [状況評価ツールを使用します](readiness-assessment-tool.md)。
3. [ゲスト アカウントの前提条件](guest-accounts.md)
4. [Microsoft マネージド デスクトップのネットワーク構成](network.md)
5. [Microsoft マネージド デスクトップ用に証明書とネットワーク プロファイルを準備する](certs-wifi-lan.md)
6. [Microsoft マネージド デスクトップ用にオンプレミス リソース アクセスを準備する](authentication.md)
7. [Microsoft マネージド デスクトップのアプリ](apps.md)
8. [Microsoft マネージド デスクトップ用に、マップされたドライブを準備する](mapped-drives.md)
9. [印刷リソースの準備Microsoft マネージド デスクトップ](printing.md)する (この記事)
