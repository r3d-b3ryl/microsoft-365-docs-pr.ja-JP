---
title: Microsoft マネージドデスクトップの役割と責任
description: このトピックでは、microsoft が microsoft マネージドデスクトップで提供する役割と責任について説明します。
keywords: microsoft マネージドデスクトップ、microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 161be07907754cdd7a0cd88dd3342d4b5e3c72e4
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283560"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Microsoft マネージドデスクトップの役割と責任


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

組織が microsoft マネージドデスクトップに登録されている場合、microsoft は何を行いますか? 組織の責任は何ですか。

## <a name="microsofts-roles-and-responsibilities"></a>Microsoft の役割と責任

Microsoft によって提供される主な役割と責任は、以下のとおりです。

役割または責任 | 説明
--- | ---
MDM ポリシーの管理 | Microsoft は、ベストプラクティスに従って MDM ポリシーを適用し、ポリシーの変更に対する要求を検討します。 また、[デバイスポリシー](../service-description/device-policies.md)で規定されているように、テナントに変更を加えます。
エンドユーザーサポート | microsoft は、すべての登録ユーザーのために、microsoft のすべての管理対象デスクトップデバイスにプレインストールされている Get Help アプリを使用して、デバイス、Windows、および Office 製品スイートのエンドユーザーサポートを提供します。 
Microsoft Managed Desktop service サポート | microsoft は、microsoft Managed Desktop Operations Team を使用して、お客様の IT 部門にサポートを提供します。 このチームは、お客様の Microsoft Managed Desktop environment の技術的なトラブルシューティング、変更要求、インシデント管理をサポートします。 詳細については、「 [Microsoft マネージドデスクトップの管理者サポート](../working-with-managed-desktop/admin-support.md)」を参照してください。
セキュリティの監視 | microsoft は、Windows Defender ATP を使用して、お客様の microsoft Managed Desktop デバイスを監視します。 microsoft Managed Desktop Security Operations Center (SOC) によって脅威が検出された場合、microsoft はお客様に通知し、デバイスを分離して、問題をリモートで修正します。 詳細については、「 [Security](../service-description/security.md)」を参照してください。
更新の監視と管理 | microsoft は、お客様の microsoft Managed Desktop デバイスを積極的に監視し、microsoft Windows および microsoft Office の最新の品質および機能の更新プログラムがインストールされていることを確認します。 詳細については、「[更新プログラムの処理方法](../service-description/updates.md)」を参照してください。
ユーザーとデバイスのグループ化 | Microsoft Managed Desktop operations team は、IT 運用の一部として必要なデバイスとユーザーグループを作成し、管理します。 これらのグループへのメンバーシップまたは構成の変更は許可されていません。 これらのグループを変更すると、予期しないデバイス構成が発生し、機能が失われる可能性があります。 これらのグループに関する問題または質問が一度確立されると、IT 管理者は Microsoft マネージドデスクトップ操作に問い合わせることができます。 詳細については、「 [Microsoft マネージドデスクトップの管理者サポート](../working-with-managed-desktop/admin-support.md)」を参照してください。

## <a name="your-roles-and-responsibilities"></a>自分の役割と責任

以下は、Microsoft によって提供されていないが、正常に展開するために必要な、一般的な役割と責任のセットの追加です。 これは網羅的なものではありませんが、ほとんどの組織に適用されます。 Microsoft とお客様との共有 responsibilties の両方について、以下にいくつかの項目があります。 

役割または責任 | 説明
--- | ---
変更管理 | microsoft は、microsoft の管理されたデスクトップ環境に変更を加える必要がある場合に、事前にお客様に通知します。 お客様には、独自の変更管理プロセスを用意し、Microsoft の管理されたデスクトップ運用チームで担当の連絡先を設定する必要があります。 お客様は、これらの変更を確認して承認するためのリソースも必要です。 詳細については、「[操作と監視](../service-description/operations-and-monitoring.md)」を参照してください。  
ID 管理 | お客様は、ユーザーアカウントを作成し、ユーザーをグループに割り当て、メタデータを最新の状態に維持する責任があります。 
Office 365 の構成と管理 | Microsoft は、Office アプリケーションがエンドユーザーに展開されることを保証する責任を担います。これらのアプリケーションは、最新の状態に保たれます。 <br><br> お客様は、Exchange Online 管理の責任を含む Office 365 のサービスとポリシーを管理する責任があります。<br>-電子メール管理<br>-メールボックスとルールの構成<br>-オンプレミスの Exchange 管理<br><br>お客様は、Office 365 管理ポータルで設定されているコラボレーションツール、SharePoint server 管理、ドメイン管理、セキュリティおよび情報ポリシーにも責任を担います。 
エンドユーザーサポート | お客様は、以下のことをエンドユーザーにサポートする責任を負います。 <br>-サイトインフラストラクチャ: ネットワークとインターネットのすべての接続、VPN インフラストラクチャとクライアントの構成、ローカルの会議室装置、プリンター、プロキシサーバーと構成、ファイアウォール。<br><br>-企業全体にわたるクラウドリソース: 電子メール、SharePoint、コラボレーションサービス、およびその他のクラウドインフラストラクチャは、企業全体にわたるテクノロジのフットプリントに関連しています。<br><br>-基幹業務およびその他の会社固有のアプリケーション。
アプリ | Microsoft は、要求時に Intune を使用して承認済みアプリケーションの展開ガイダンスを提供します。<br><br>お客様は次のことを担当します。<br>-組織のアプリの一覧を提供する (Office 365 アプリの外)<br>-アプリライセンス管理<br>–正しい種類とライセンスの数量がある<br>-アプリの割り当て<br>-Azure AD ユーザーグループへのアプリの割り当て<br>-アプリの更新<br>–アプリの機能とセキュリティ更新プログラムを監視、パッケージ化、および展開する<br>-ユーザーアプリケーションテスト (UAT)<br>-適切に展開可能なパッケージを提供する<br><br>詳細については、「[アプリ](../get-ready/apps.md)」を参照してください。
セキュリティの監視と応答 | お客様は、microsoft が管理していないデスクトップデバイスのインシデントを調査および解決し、そのサービスに影響を与える可能性のある問題があるかどうかを microsoft managed desktop Operations Team に通知する責任を負います。
運用のサポート | お客様は、お客様に推奨されるお客様の連絡先と該当分野の専門家のリストを提供する責任を担います。 microsoft では、管理されていないデスクトップの運用インシデントがある場合には、これらの機能が必要です。 <br><br>お客様は、microsoft が管理していないデスクトップデバイスおよびサービスのインシデントを調査および解決し、microsoft の管理対象デスクトップ運用チームに常に通知されるようにする責任もあります。
ネットワークインフラストラクチャ (VPN を含む) | お客様は、インターネット接続、ネットワーク制御、プロキシ構成、およびリモートを含む、すべてのネットワーク関連のインフラストラクチャとサービスのセットアップ、構成、および管理 (トラブルシューティングおよびデバッグ) を担当しています。接続インフラストラクチャ。<br><br>プロキシが (ハードウェアまたはソフトウェアで) 構成されている場合は、プロキシが許可する必要がある url のコレクションがあります。 お客様は、複数のプロキシによって競合または非互換性のトラブルシューティングを行う必要があります。 構成可能な設定を使用して、組織に固有のネットワークプロキシを追加することができます。 詳細については、「[構成可能な設定](../working-with-managed-desktop/config-setting-ref.md#proxy)」を参照してください。<br><br>詳細については、「[プロキシの構成](../get-ready/network.md)」を参照してください。
印刷 | お客様は、プリンターおよび印刷キューをインストール、管理、および管理する責任があります。 クラウド印刷は推奨されるソリューションですが、必須ではありません。 




