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
ms.openlocfilehash: b6e809505fed8b1f84eb502dc08751ad1f0b587c
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841401"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップ用に、印刷リソースを準備する

Microsoft マネージド デスクトップに登録する準備ができたら、印刷要件を評価し、環境に適切なアプローチを決定する必要があります。 次の 3 つのオプションがあります。
 
- Microsoft ユニバーサル印刷ソリューションを展開して、Microsoft マネージド デスクトップ デバイスでプリンターを簡単に検出できます。 詳細については、「ユニバーサル印刷 [とは」を参照してください](https://docs.microsoft.com/universal-print/fundamentals/universal-print-whatis)。
- カスタム PowerShell スクリプトを使用してプリンターを直接展開します。 「ローカル プリンターのセットアップ [」セクションの手順に従](#set-up-local-printers) います。
- Azure Active Directory ドメインに参加している Windows 10 デバイスと互換性のある Microsoft 以外のクラウド印刷ソリューションを使用します。 このソリューションは、Microsoft マネージド デスクトップのソフトウェア要件を満たしている必要があります。 詳しくは [、Microsoft マネージド デスクトップ アプリの要件に関するページをご覧ください](../service-description/mmd-app-requirements.md)。
 
すべての場合において、プリンター ドライバーが Microsoft Update または Microsoft Store から入手できない場合は、プリンター ドライバーを自分で入手し、Microsoft Intune を使用して Microsoft マネージド デスクトップ デバイスに展開するためにパッケージ化する必要があります。 詳しくは、「Intune スタンドアロン[- Win32 アプリ管理」をご覧ください](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)。

## <a name="set-up-local-printers"></a>ローカル プリンターをセットアップする

カスタム PowerShell スクリプトを使用してプリンターを展開し、印刷リソースを準備した場合は、次の手順に従って、共有プリンターを展開します。

1.  Microsoft マネージド デスクトップ ポータルに移動します。
2.  管理ポータルのサポート> サポート要求セクションで、プリンターの展開というラベルの付いた要求を送信し、次の詳細を提供します。
    - Microsoft マネージド デスクトップ デバイス用に展開する必要がある、プリンターの共有の場所への UNC パスすべて
    - これらの共有プリンターへのアクセスが必要なユーザー グループ
3.  管理ポータルを使用して、要求が完了した時間をお知らせします。 最初は、テスト展開グループのデバイスにのみ構成を展開します。
4.  構成が期待通り動作するかどうかをテストして確認する必要があります。 テストが完了したら **、** サポート要求の [ディスカッション] タブを使用して返信します。
5.  その後、構成を他の展開グループに展開します。
