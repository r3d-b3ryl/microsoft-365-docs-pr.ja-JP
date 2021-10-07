---
title: 準備状況評価ツール
description: 2 つのツール、実行するチェック、および結果の意味について説明します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: c584632a625ecb8597aa0c9319063e6f9198bec3
ms.sourcegitcommit: afee35210f8d68a7f20676ff2a829464b0b0adb2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2021
ms.locfileid: "60216936"
---
# <a name="readiness-assessment-tools"></a>準備状況評価ツール

Microsoft マネージド デスクトップ に登録する際に最もスムーズなエクスペリエンスを実現するために、前もって設定する必要がある設定や他のパラメーター、および満たすために特定のデバイスとネットワーク要件があります。 管理ポータルからアクセスする 1 つのツールMicrosoft マネージド デスクトップ管理関連の設定をチェックします。 ダウンロード可能な別のツールは、個々のデバイス要件とネットワーク設定をチェックします。 これらのツールを使用して、これらの設定を確認し、適切でない設定を修正するための詳細な手順を受け取ってください。

## <a name="downloadable-readiness-assessment-checker-for-devices-and-network"></a>デバイスとネットワークのダウンロード可能な準備状況評価チェッカー

ダウンロード可能な準備状況評価チェッカーの使用の詳細については、「ダウンロード可能な準備状況 [評価チェッカー」を参照してください](readiness-assessment-downloadable.md)。

## <a name="online-readiness-assessment-tool-for-management-settings"></a>管理設定のオンライン準備評価ツール

オンライン[ツールは](https://aka.ms/mmdart)、Microsoft エンドポイント マネージャー (具体的には Microsoft Intune)、Azure Active Directory (Azure AD)、Microsoft 365 の設定をチェックして、Microsoft マネージド デスクトップ で動作するようにします。 Microsoft マネージド デスクトップ組織 (テナント) で前回チェックを実行した後、これらのチェックに関連付けられたデータAD保持されます。 12 か月後、識別されていない形式で保持されます。 収集したデータを削除できます。

少なくともグローバル リーダーまたは Intune 管理者の役割を持つユーザーは、このツールを実行できますが、2 つのチェック[](readiness-assessment-fix.md#multifactor-authentication)[(条件付](readiness-assessment-fix.md#conditional-access-policies)きアクセス ポリシーと多要素認証には追加のアクセス許可が必要です)。

> [!IMPORTANT]  
> オンラインの準備状況評価ツールを使用すると、初めてMicrosoft マネージド デスクトップ準備を確認できます。 組織が既に組織に登録されているMicrosoft マネージド デスクトップ、このツールを使用しない。

評価ツールは、次の項目をチェックします。

## <a name="microsoft-intune-settings"></a>Microsoft Intune設定

|小切手  |説明  |
|---------|---------|
|自動パイロット展開プロファイル     | Autopilot 展開プロファイルの割り当てがすべてのデバイスに適用されないMicrosoft マネージド デスクトップします。        |
|証明書コネクタ     | 証明書コネクタの状態をチェックして、アクティブな状態を確認します。   |
|条件付きアクセス     | 条件付きアクセス ポリシーがすべてのユーザーに割り当てられていないMicrosoft マネージド デスクトップします。     |
|デバイス コンプライアンス ポリシー     | Intune コンプライアンス ポリシーがすべてのユーザーに割り当てられていないMicrosoft マネージド デスクトップします。     |
|デバイス構成プロファイル     | 構成プロファイルがすべてのユーザーまたはすべてのデバイスに割り当てられていないMicrosoft マネージド デスクトップします。      |
|デバイスの種類の制限     | 組織内のWindows 10 Intune への登録が許可されているチェック        |
|登録ステータス ページ     | [登録の状態] ページが有効になっていないか確認する      |
|Intune の登録     | Azure 組織Windows 10デバイスが自動的AD Intune に登録されるのを確認します。         |
|ビジネス向け Microsoft Store     | Intune でビジネス向け Microsoft Store同期が有効になっているか確認する        |
|多要素認証 | 複数要素認証がサービス アカウントに適用Microsoft マネージド デスクトップします。
|PowerShell スクリプト     | デバイスをWindows PowerShell *する方法で*、スクリプトが割り当てられていないMicrosoft マネージド デスクトップします。    |
|地域     | 地域がユーザーによってサポートMicrosoft マネージド デスクトップ        |
|セキュリティ基本計画     | セキュリティ 基準プロファイルがすべてのユーザーまたはすべてのデバイスを対象としていないMicrosoft マネージド デスクトップします。        |
|Windowsアプリ     | デバイスに割り当てるアプリをMicrosoft マネージド デスクトップする      |
|Windows Hello for Business     | Business のWindows Helloが有効になっているか確認する        |
|Windows 10更新リング     | Intune の "Windows 10 更新リング" ポリシーがすべてのユーザーまたはすべてのデバイスを対象としていないMicrosoft マネージド デスクトップします。      |


## <a name="azure-active-directory-settings"></a>Azure Active Directory設定

|小切手  |説明  |
|---------|---------|
|"アドホック" サブスクリプションによる Enterpriseローミング     | ("false" に設定されている場合) 状態ローミングが正しく動作しない可能性があるEnterpriseを確認する方法について説明します。  |
|Enterprise State Roaming     | 状態ローミングが有効になっているEnterprise確認する方法について説明します。       |
|ライセンス     | 必要なライセンスを [取得したチェック](prerequisites.md#more-about-licenses)         |
|多要素認証     | 多要素認証がすべてのユーザーに適用されないMicrosoft マネージド デスクトップします。|
|セキュリティ アカウント名   | ユーザー名が、独自の使用のために予約Microsoft マネージド デスクトップと競合しなか        |
|セキュリティ管理者の役割     | Microsoft Defender for Endpoint でセキュリティ リーダー、セキュリティ オペレーター、またはグローバル リーダーの役割を持つユーザーにそれらの役割が割り当てられているか確認します。         |
|セキュリティの既定値 | Azure 組織でセキュリティADが有効になっているかどうかを確認Azure Active Directory |
|セルフサービスによるパスワードのリセット     | セルフサービス パスワードのリセットが有効になっているか確認する        |
|標準ユーザー ロール     | ユーザーが標準ユーザーであり、ローカル管理者権限を持たなかっているのを確認します。         |


## <a name="microsoft-365-apps-for-enterprise-settings"></a>Microsoft 365 Apps for enterprise設定

|小切手  |説明  |
|---------|---------|
|OneDrive for Business     | サポートされていない設定OneDrive for Business使用するかどうかを確認します。        |


チェックごとに、ツールは次の 4 つの結果のいずれかを報告します。


|結果  |意味  |
|---------|---------|
|準備完了     | 登録を完了する前に、アクションは必要ありません。        |
|アドバイザリ    | 登録とユーザーの最適なエクスペリエンスを得るには、ツールの手順に従います。 登録 *は* 完了できますが、最初のデバイスを展開する前に、これらの問題を修正する必要があります。        |
|使用不可能 | *これらの問題を* 解決しない場合、登録は失敗します。 ツールの手順に従って解決します。        |
|Error | 使用している Azure Active Director (AD) ロールには、このチェックを実行するための十分なアクセス許可が付与されません。 |

## <a name="after-enrollment"></a>登録後

アプリへの登録が完了したらMicrosoft マネージド デスクトップ、Intune と Azure の特定の設定に戻ってADしてください。 詳細については、「登録後に [設定を調整する」を参照してください](../get-started/conditional-access.md)。

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>インストールの準備を行うMicrosoft マネージド デスクトップ

1. [Microsoft マネージド デスクトップの前提条件](prerequisites.md)を確認します。
2. 準備状況評価ツールを実行します (この記事)。
1. [ポータル サイト](../get-started/company-portal.md)を購入します。
1. [ゲスト アカウントの前提条件](guest-accounts.md)を確認します。
1. [ネットワーク構成](network.md)をチェックします。
1. [証明書とネットワーク プロファイル](certs-wifi-lan.md)を準備します。
1. [データへのユーザー アクセスを準備します](authentication.md)。
1. [アプリを準備します](apps.md)。
1. [マップ済みドライブを準備します](mapped-drives.md)。
1. [印刷リソースを準備します](printing.md)。
1. [デバイス名](address-device-names.md)をアドレス指定します。
