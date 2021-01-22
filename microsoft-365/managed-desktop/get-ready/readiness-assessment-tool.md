---
title: 準備状況評価ツール
description: 2 つのツール、実行するチェック、および結果の意味について説明します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 9fbd24185288265d698288e0d5e63e8b3c2afd10
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921848"
---
# <a name="readiness-assessment-tools"></a>準備状況評価ツール

Microsoft マネージド デスクトップに登録するときに可能な限りスムーズなエクスペリエンスを実現するために、設定や他のパラメーターを前もって設定する必要があります。また、満たさなければならないデバイスとネットワークの要件があります。 Microsoft マネージド デスクトップ管理ポータルからアクセスする 1 つのツールは、管理関連の設定をチェックします。 ダウンロード可能な別のツールは、個々のデバイス要件とネットワーク設定をチェックします。 これらのツールを使用すると、これらの設定を確認し、適切でない設定を修正するための詳細な手順を受け取る方法を確認できます。

## <a name="downloadable-readiness-assessment-checker-for-devices-and-network"></a>デバイスとネットワークのダウンロード可能な準備状況評価チェック ツール

ダウンロード可能な準備状況評価チェックツールの使用の詳細については、「ダウンロード可能な準備状況の評価チェック [」を参照してください](readiness-assessment-downloadable.md)。

## <a name="online-readiness-assessment-tool-for-management-settings"></a>管理設定用のオンライン準備状況評価ツール

オンライン ツールは、Microsoft Endpoint Manager (具体的には Microsoft Intune)、Azure Active Directory (Azure AD)、Microsoft 365 の設定をチェックして、Microsoft マネージド デスクトップで動作するようにします。 Microsoft マネージド デスクトップでは、これらのチェックに関連付けられたデータが、Azure AD 組織 (テナント) で最後にチェックを実行した後、12 か月間保持されます。 12 か月後は、特定されていない形式で保持されます。 収集するデータを削除することができます。

少なくとも Intune 管理者ロールを持つユーザーは、このツールを実行できますが、2 つのチェック[(](readiness-assessment-fix.md#conditional-access-policies)条件付[](readiness-assessment-fix.md#multifactor-authentication)きアクセス ポリシーと多要素認証には追加のアクセス許可が必要です)。
 
評価ツールは、次の項目をチェックします。

## <a name="microsoft-intune-settings"></a>Microsoft Intune の設定

|小切手  |説明  |
|---------|---------|
|Autopilot 展開プロファイル     | Autopilot 展開プロファイルの割り当てがすべてのデバイスに適用されないか確認します (プロファイルを Microsoft マネージド デスクトップ デバイスに割り当てない必要があります)。       |
|証明書コネクタ     | 証明書コネクタの状態をチェックして、アクティブな状態を確認します。   |
|条件付きアクセス     | 条件付きアクセス ポリシーがすべてのユーザーに割り当てられていないか確認します (条件付きアクセス ポリシーを Microsoft マネージド デスクトップ サービス アカウントに割り当てない必要があります)。    |
|デバイス コンプライアンス ポリシー     | Intune コンプライアンス ポリシーがすべてのユーザーに割り当てられていないか確認します(ポリシーを Microsoft マネージド デスクトップ デバイスに割り当てない必要があります)。    |
|デバイス構成プロファイル     | 構成プロファイルがすべてのユーザーまたはすべてのデバイスに割り当てられていないか確認します (構成プロファイルを Microsoft マネージド デスクトップ デバイスに割り当てない必要があります)。     |
|デバイスの種類の制限     | 組織内の Windows 10 デバイスで Intune への登録が許可されていないことを確認します。        |
|[登録の状態] ページ     | [登録状態] ページが有効になっていないか確認します。      |
|Intune 登録     | Azure 組織の Windows 10 デバイスAD Intune に自動的に登録されるのを確認します。         |
|ビジネス向け Microsoft Store     | ビジネス向け Microsoft Store が有効であり、Intune と同期されているのを確認します。        |
|多要素認証 | Microsoft マネージド デスクトップ サービス アカウントに多要素認証が適用されていないか確認します。
|PowerShell スクリプト     | Microsoft マネージド Windows PowerShellターゲットとなる方法 *でスクリプト* が割り当てられていないか確認します。    |
|Region     | 地域が Microsoft マネージド デスクトップでサポートされていないことを確認します。        |
|セキュリティベースライン     | セキュリティ基本計画プロファイルが、すべてのユーザーまたはすべてのデバイスを対象としていないか確認します (セキュリティ基本ポリシーは、Microsoft マネージド デスクトップ デバイスを対象とすべきではありません)。       |
|Windows アプリ     | Microsoft マネージド デスクトップ デバイスに割り当てるアプリを確認する      |
|Windows Hello for Business     | Windows Hello for Business が有効になっているか確認する        |
|Windows 10 更新リング     | Intune の "Windows 10 更新リング" ポリシーが、すべてのユーザーまたはすべてのデバイスを対象としていない(このポリシーは、Microsoft マネージド デスクトップ デバイスを対象としていない) か確認します。     |


## <a name="azure-active-directory-settings"></a>Azure Active Directory の設定

|小切手  |説明  |
|---------|---------|
|Enterprise State Roaming の "アドホック" サブスクリプション     | ("false" に設定されている場合)、エンタープライズ状態ローミングが正しく動作しない可能性がある設定を確認する方法について説明します。  |
|Enterprise State Roaming     | Enterprise State Roaming が有効になっているか確認する方法について説明します。       |
|ライセンス     | 必要なライセンスを [取得したチェック](prerequisites.md#more-about-licenses)         |
|多要素認証     | 多要素認証がすべてのユーザーに適用されていないか確認します (多要素認証を Microsoft マネージド デスクトップ サービス アカウントに誤って適用しないようにする必要があります)。|
|セキュリティ アカウント名   | ユーザー名が、Microsoft マネージド デスクトップで独自の使用のために予約されているユーザー名と競合しなかからなかっているのを確認します。        |
|セキュリティ管理者ロール     | セキュリティ 閲覧者、セキュリティオペレーター、またはグローバル 閲覧者の役割を持つユーザーに、エンドポイント用 Microsoft Defender でそれらの役割が割り当てられているか確認します。         |
|セキュリティの既定値 | Azure Active Directory で Azure ADセキュリティの既定値が有効になっているかどうかを確認します。 |
|セルフサービスによるパスワードのリセット     | セルフサービスによるパスワードのリセットが有効になっているか確認する        |
|標準ユーザー ロール     | ユーザーが標準ユーザーであり、ローカル管理者権限を持たなことを確認します。         |


## <a name="microsoft-365-apps-for-enterprise-settings"></a>Microsoft 365 Apps for enterprise の設定

|小切手  |説明  |
|---------|---------|
|OneDrive for Business     | OneDrive for Business でサポートされていない設定が使用されているかどうかを確認します。        |


チェックごとに、ツールは次の 4 つの結果のいずれかを報告します。


|結果  |意味  |
|---------|---------|
|準備完了     | 登録を完了する前に、何もする必要はありません。        |
|アドバイザリ    | 登録とユーザーに最適なエクスペリエンスを得る場合は、ツールの手順に従ってください。 登録 *は* 完了できますが、最初のデバイスを展開する前に、これらの問題を修正する必要があります。        |
|使用不可能 | *これらの問題を* 解決しない場合、登録は失敗します。 ツールの手順に従って解決します。        |
|Error | 使用している Azure Active Director (AD) ロールに、このチェックを実行するための十分なアクセス許可がない。 |

## <a name="after-enrollment"></a>登録後

Microsoft マネージド デスクトップへの登録が完了したら、Intune と Azure の特定の設定に戻り、調整ADしてください。 詳細については、「登録後に [設定を調整する」を参照してください](../get-started/conditional-access.md)。
