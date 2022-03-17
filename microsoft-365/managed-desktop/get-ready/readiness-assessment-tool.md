---
title: 準備状況の評価ツール
description: 2 つのツール、それらが実行するチェック、および結果の意味について説明します
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: 8d949b13203aaeab51d2518f16650ba6df832195
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2022
ms.locfileid: "63525640"
---
# <a name="readiness-assessment-tools"></a>準備状況の評価ツール

Microsoft Managed Desktop に登録するときに可能な限りスムーズなエクスペリエンスを実現するには、事前に設定する必要のある設定やその他のパラメーター、および満たす必要のある特定のデバイスとネットワークの要件があります。

Microsoft Managed Desktop 管理者ポータルからアクセスする 1 つのツールは、管理関連の設定をチェックします。 ダウンロード可能な別のツールは、個々のデバイス要件とネットワーク設定をチェックします。 これらのツールを使用して、これらの設定を確認し、正しくないものを修正するための詳細な手順を受け取ることができます。

## <a name="downloadable-readiness-assessment-checker-for-devices-and-network"></a>デバイスとネットワーク用のダウンロード可能な準備評価チェック

ダウンロード可能な準備評価チェックーの使用の詳細については、「[ダウンロード可能な準備評価チェック](readiness-assessment-downloadable.md)」を参照してください。

## <a name="online-readiness-assessment-tool-for-management-settings"></a>管理設定のためのオンライン準備評価ツール

オンライン [ツールは](https://aka.ms/mmdart)、Microsoft エンドポイント マネージャー (具体的には Microsoft Intune)、Azure Active Directory (Azure AD)、Microsoft 365 の設定をチェックして、Microsoft マネージ デスクトップで動作します。

Microsoft Managed Desktop は、Azure AD 組織 (テナント) で最後にチェックを実行してから 12 か月間、これらのチェックに関連付けられたデータを保持します。 12 か月後、匿名化された形式で保持します。 収集したデータを削除することを選択できます。

少なくともグローバル リーダーまたは Intune 管理者の役割を持つユーザーは、このツールを実行できますが、2 つの[チェック (条件付](readiness-assessment-fix.md#conditional-access-policies) きアクセス ポリシーと多要素 [認証) には](readiness-assessment-fix.md#multi-factor-authentication)追加のアクセス許可が必要です。

> [!IMPORTANT]  
> オンライン準備評価ツールは、Microsoft マネージド デスクトップに初めて登録する準備ができているかどうかを確認するのに役立ちます。 組織が既に Microsoft マネージド デスクトップに登録されている場合は、このツールを使用しないでください。

評価ツールは次の項目をチェックします。

## <a name="microsoft-intune-settings"></a>Microsoft Intune 設定

次に示す設定Microsoft Intuneします。

| チェック | 説明 |
| ------ | ------ |
| Autopilot 展開プロファイル | Autopilot 展開プロファイルの割り当てがすべてのデバイスに適用されないか確認します。 <br><br> プロファイルを **Microsoft 管理** デスクトップ デバイスに割り当てない必要があります。 |
| 証明書コネクタ | 証明書コネクタがアクティブな状態を確認します。 |
| 条件付きアクセス | 条件付きアクセス ポリシーがすべてのユーザーに割り当てられていないか確認します。 <br><br> 条件付きアクセス ポリシーは **、** Microsoft Managed Desktop サービス アカウントに割り当てない必要があります。 |
| デバイス コンプライアンス ポリシー | Intune コンプライアンス ポリシーがすべてのユーザーに割り当てられていないか確認します。 <br><br> ポリシーは、 **Microsoft** 管理デスクトップ デバイスに割り当てない必要があります。 |
| デバイスの構成プロファイル | 構成プロファイルがすべてのユーザーまたはすべてのデバイスに割り当てられていないか確認します。 <br><br> 構成プロファイルは **、Microsoft** 管理デスクトップ デバイスに割り当てない必要があります。 |
| デバイスの種類の制限 | 組織内のWindows 10 Intune への登録が許可されていないことを確認します。 |
| 登録ステータス ページ | [登録状態] ページが有効になっていないか確認します。 |
| Intune の登録 | 組織のWindows 10デバイスが自動的Azure AD Intune に登録されるのを確認します。 |
| ビジネス向け Microsoft Store | Intune でビジネス向け Microsoft Storeが有効で同期されているのを確認します。 |
| 多要素認証 | 多要素認証が Microsoft Managed Desktop サービス アカウントに適用されていないか確認します。 |
| PowerShell スクリプト | Microsoft Managed Desktop Windows PowerShellターゲットとする方法で、スクリプトが割り当てられていないか確認します。 |
| Region | 地域が Microsoft Managed Desktop でサポートされていないことを確認します。 |
| セキュリティ基本計画 | セキュリティ 基準プロファイルがすべてのユーザーまたはすべてのデバイスを対象としないか確認します。 <br><br> セキュリティ ベースライン ポリシーは、 **Microsoft 管理** デスクトップ デバイスを対象とすべきではありません。 |
| Windows アプリ | Microsoft Managed Desktop デバイスに割り当てるアプリを確認します。 |
| Windows Hello for Business | Business のWindows Helloが有効になっているか確認します。 |
| Windows 10 更新リング | Intune の "更新リングWindows 10" ポリシーがすべてのユーザーまたはすべてのデバイスを対象としないか確認します。 <br><br> ポリシーは、 **Microsoft** 管理デスクトップ デバイスを対象とすべきではありません。 |

## <a name="azure-active-directory-settings"></a>Azure Active Directory の設定

次に示す設定Azure Active Directory示します。

| チェック | 説明 |
| ----- | ----- |
| Enterprise State Roaming の "アドホック" サブスクリプション | "false" に設定すると、状態ローミングが正常に動作しないEnterprise設定を確認する方法について説明します。 |
| Enterprise State Roaming | 状態ローミングが有効になっているEnterprise確認する方法について説明します。 |
| ライセンス | 必要なライセンスを取得したと確認 [します](prerequisites.md#more-about-licenses)。 |
| 多要素認証 | 多要素認証がすべてのユーザーに適用されていないか確認します。 <br><br> 多要素認証 **を Microsoft Managed** Desktop サービス アカウントに誤って適用しないようにする必要があります。 |
| セキュリティ アカウント名 | Microsoft Managed Desktop が独自に使用するために予約したユーザー名と競合が生じなか確認します。 |
| セキュリティ管理者の役割 | セキュリティ リーダー、セキュリティ オペレーター、またはグローバル リーダーの役割を持つユーザーに、Microsoft Defender for Endpoint でそれらの役割が割り当てられているか確認します。 |
| セキュリティの既定値 | 組織でセキュリティAzure ADが有効になっているかどうかを確認Azure Active Directory。 |
| セルフサービスによるパスワードのリセット | セルフサービス パスワードのリセットが有効になっているか確認します。 |
| 標準ユーザーの役割 | ユーザーが標準ユーザーであり、ローカル管理者権限を持たなかったか確認します。 |

## <a name="microsoft-365-apps-for-enterprise-settings"></a>Microsoft 365 Apps設定Enterpriseする

次に示すのは、Microsoft 365 Apps設定Enterpriseです。

| チェック | 説明 |
| ----- | ----- |
| OneDrive for Business | OneDrive for Business がサポートされていない設定を使用しているかどうかを確認します。 |

チェックごとに、ツールは 4 つの考えられる結果のいずれかを報告します。

| 結果 | 意味 |
| ----- | ----- |
| 準備完了 | 登録を完了する前にアクションは必要ありません。 |
| アドバイザリ | 登録とユーザーにとって最高のエクスペリエンスを得るには、ツールの手順に従ってください。 <br><br> 登録を完了することは *できます* が、最初のデバイスを展開する前にこれらの問題を修正する必要があります。 |
| 使用不可能 | これらの問題を修正しないと、**登録は失敗します**。 <br><br> ツールの手順に従って解決します。 |
| Error | 使用してい るAzure Active Director (AD) の役割には、このチェックを実行するための十分なアクセス許可がありません。 |

## <a name="after-enrollment"></a>登録した後

Microsoft Managed Desktop への登録が完了したら、戻って特定の Intune および Azure AD 設定を調整することを忘れないでください。 詳細については、「登録後に [設定を調整する」を参照してください](../get-started/conditional-access.md)。

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>Microsoft Managed Desktop の準備をする手順

1. [Microsoft マネージド デスクトップの前提条件](prerequisites.md)を確認します。
2. 準備評価ツール (この記事) を実行します。
3. [ポータル サイト](../get-started/company-portal.md)を購入します。
4. [ゲスト アカウントの前提条件](guest-accounts.md)を確認します。
5. [ネットワーク構成](network.md)をチェックします。
6. [証明書とネットワーク プロファイル](certs-wifi-lan.md)を準備します。
7. [データへのユーザー アクセスを準備します](authentication.md)。
8. [アプリを準備します](apps.md)。
9. [マップ済みドライブを準備します](mapped-drives.md)。
10. [印刷リソースを準備します](printing.md)。
11. [デバイス名](address-device-names.md)をアドレス指定します。
