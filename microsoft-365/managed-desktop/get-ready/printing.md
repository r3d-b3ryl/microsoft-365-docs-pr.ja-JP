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
ms.openlocfilehash: 3decc7d67decc5557e7921e68108e2ddb447f0fd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924554"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップ用に、印刷リソースを準備する

Microsoft Managed Desktop に登録する準備が整ったら、印刷要件を評価し、環境に適切なアプローチを決定する必要があります。 次の 3 つのオプションがあります。
 
- Microsoft ユニバーサル 印刷ソリューションを展開して、Microsoft Managed Desktop デバイスがプリンターを簡単に検出できます。 詳細については [、「What is Universal Print 」を参照してください](/universal-print/fundamentals/universal-print-whatis)。
- カスタム PowerShell スクリプトを使用してプリンターを直接展開します。 「ローカル プリンターのセットアップ [」セクションの手順に従](#set-up-local-printers) います。
- Azure Active Directory ドメインに参加している Windows 10 デバイスと互換性のある Microsoft 以外のクラウド印刷ソリューションを使用します。 ソリューションは、Microsoft Managed Desktop のソフトウェア要件を満たす必要があります。 詳細については [、「Microsoft Managed Desktop アプリの要件」を参照してください](../service-description/mmd-app-requirements.md)。
 
すべての場合、プリンター ドライバーが Microsoft Update または Microsoft Store から利用できない場合は、それらを取得し、Microsoft Intune を使用して Microsoft 管理デスクトップ デバイスに展開するためにパッケージ化する必要があります。 詳細については [、「Intune スタンドアロン - Win32 アプリ管理」を参照してください。](/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>ローカル プリンターのセットアップ

カスタム PowerShell スクリプトを使用してプリンターを展開し、印刷リソースを準備した場合は、次の手順に従って共有プリンターを展開します。

1.  Microsoft Managed Desktop ポータルに移動します。
2.  次の詳細を提供 *して、管理* ポータルの [サポート >サポート要求] セクションで、プリンターの展開というラベルの付いた要求を送信します。
    - Microsoft Managed Desktop デバイスに展開する必要がある共有プリンターの場所へのすべての UNC パス
    - これらの共有プリンターへのアクセスを必要とするユーザー グループ
3.  管理ポータルを使用して、要求がいつ完了したのかお知らせします。 最初は、テスト展開グループ内のデバイスにのみ構成を展開します。
4.  構成が期待通り動作するかどうかをテストして確認する必要があります。 サポート要求の [ **ディスカッション]** タブを使用して返信し、テストが完了したらお知らせします。
5.  その後、構成を他の展開グループに展開します。