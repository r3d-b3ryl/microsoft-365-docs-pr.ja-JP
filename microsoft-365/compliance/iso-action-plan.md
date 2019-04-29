---
title: Microsoft 365 ISO 27001 のアクション プラン - 最初の 30 日間、90 日間、およびそれ以降の優先事項
description: 国際標準化機構 (ISO) の要件を満たすための取り組みで利用できる、優先順位付けされたアクション プラン
keywords: Microsoft 365、Microsoft 365 Education、Microsoft 365 ドキュメント、ISO, ISO 27001
author: BrendaCarter
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
manager: laurawi
audience: itpro
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 3f81ad10d4549f9f28b5df4a0e090fb38a54bf6f
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283459"
---
# <a name="microsoft-365-iso-27001-action-plan--top-priorities-for-your-first-30-days-90-days-and-beyond"></a>Microsoft 365 ISO 27001 のアクション プラン - 最初の 30 日間、90 日間、およびそれ以降の優先事項

国際標準化機構 (ISO) は、任意の国際規格を策定する独立の非政府組織です。国際電気標準会議 (IEC) は、電気、電子、および関連技術に関する国際規格の作成と公開を牽引しています。ISO/IEC 27000 ファミリーの標準規格は、情報資産のセキュリティを維持するのに役立つ制御とメカニズムを概説するものです。

ISO/IEC 27001 は、情報セキュリティ管理システム (ISMS) を実装するための国際規格です。ISMS には、あらゆる種類の組織における情報資産セキュリティの信頼できる管理に必須とされる、使用される必要な方法と関連する証拠について記載されています。  

この記事は、ISO/IEC 27001 の要件を満たすための取り組みで利用できる、優先順位付けされたアクション プランについて説明しています。このアクション プランは、法令遵守を専門とする Microsoft のパートナーである Protiviti と提携して作成されました。Microsoft Ignite でこのアクション プランを使用する方法については、Maithili Dandige (Microsoft) と Antonio Maio (Protiviti) によるセッション「[Microsoft 365 準拠のパスと情報保護戦略を図化する](https://myignite.techcommunity.microsoft.com/sessions/65720?source=sessions)」に参加してご確認ください。


## <a name="action-plan-outcomes"></a>アクション プランの結果
これらの推奨事項は、3 つのフェーズで論理的な順序で提供され、以下の結果を伴います。 

|||
|:-----|:-----|
|**フェーズ**|**結果**|
|30 日間|**ISO 27001 のガバナンスおよびコンプライアンス要件を理解します。**<br>• リスク評価を実施し、評価の結果に対しリスク管理と緩和を調整します。<br>• Microsoft のコンプライアンス マネージャーを使用して、コンプライアンスのリスクを評価および管理します。<br>• 14 の ISO 27001 グループごとに標準業務手順書 (SOP) を作成します。<br><br>**機密データと資産を特定、分類、保護できるようにするための、情報分類、保持ポリシー、ツールの組織への展開を計画します。**<br>• Azure Information Protection のアプリケーションとポリシーによって、どのようにユーザーが機密度の視覚的なマーキングやメタデータを、文書やメールに簡単に適用することができるかについて説明します。組織の情報分類スキーマと共に、教育および展開計画を作成します。<br>• ユーザーがレコードの保持および保護ポリシーをコンテンツに簡単に適用できるようにするために、Office 365 ラベルを組織に展開することを検討します。情報記録保持の法的要件に従って組織のラベルを計画し、教育および展開計画も計画します。<br><br>**標準業務手順書 (SOP) の一環として監査および責任ポリシーを作成することにより、情報セキュリティに関連する記録が紛失、削除、改ざん、または不正アクセスされないようにします。**<br>• 監査ログ (メールボックス監査など) を有効にして、Office 365 に潜在的な悪意のあるアクティビティがないかを監視し、データ侵害のフォレンジック分析を可能にします。<br>• 通常のスケジュールで Office 365 テナントの監査ログを検索し、テナントの構成設定に加えられた変更を確認します。<br>• ユーザー アカウントの権限の昇格が発生した場合など、機密性の高いアクティビティに対するアラート ポリシーを有効にします。<br>• Office 365 監査ログ データを長期間保存するには、Office 365 管理アクティビティ API リファレンスを使用して、セキュリティ情報およびイベント管理 (SIEM) ツールと統合します。<br><br>**組織のための管理者ロールおよびセキュリティ ロールと共に、業務の分離に関連する適切な方針を定義します。**<br>• Office 365 の管理者ロールを利用して、管理業務の分離を可能にします。<br>• 一人の管理者が必要以上に大きいアクセス権を持たないようにするため、アクセス許可を分割します。
|90 日間|**Microsoft 365 のセキュリティ機能を使用して環境へのアクセスを制御し、定義した標準業務手順書 (SOP) に従って組織の情報と資産を保護します。**<br>• 多要素認証や先進認証などの ID と認証のソリューションを有効にして、管理者とエンド ユーザーのアカウントを保護します。<br>• ユーザー アカウントの資格情報を管理および保護するための強力なパスワード ポリシーを確立します。<br>• 機密データをメールで送信する際にエンド ユーザーが組織の SOP に準拠できるようにするメッセージ暗号化機能を設定し、展開します。<br>• 悪意のあるコードから保護して、データ侵害の防止策と対応策を実装します。<br>• データ損失防止 (DLP) ポリシーを構成して、機密データの特定、保護、およびアクセス制御を行います。<br>• 確実に企業ポリシーに従った形で、機密データが保存され、アクセスされるようにします。<br>• フィッシング メールや悪意のあるリンクや添付ファイルを含む Office ドキュメントなど、最も一般的な攻撃ベクトルを防止します。
|90 日以降|**Microsoft 365 の高度なデータ ガバナンス ツールと情報保護を使用して、個人データの継続的な管理プログラムを実装します。**<br>• ドキュメントやメールの個人情報を自動的に識別します。<br>• モバイル デバイスで保存およびアクセスされる機密データを組織全体で保護し、データに対して必ず準拠した会社のデバイスを使用するようにします。<br><br>**Microsoft 365 および他のクラウド アプリケーション間で進行中のコンプライアンスを監視します。**<br>• 標準業務手順書 (SOP) に対するパフォーマンスを評価するには、Microsoft コンプライアンス マネージャーを使用して、組織の情報セキュリティ ポリシーとその実装に対する定期的な評価を実行します。<br>• 情報セキュリティ管理システムを継続的に評価および監視します。<br>• 高レベルのアクセス許可を持つすべてのユーザーおよびグループ (特権ユーザーまたは管理ユーザー) を制御し定期的に評価します。<br>• 特権 ID を保護し、特権アクセスを厳密に制御するための Microsoft 365 の機能を展開および構成します。<br>• 標準業務手順書 (SOP) の一環として、Office 365 監査ログを検索し、テナントの構成設定の変更、エンド ユーザーの権限昇格、および危険なユーザー アクティビティを確認します。<br>• クラウド アプリケーションの組織の使用状況を監視し、高度な警告ポリシーを実装します。<br>• 危険なアクティビティを追跡して、潜在的な悪意のある管理者を特定し、データ侵害を調査し、コンプライアンス要件が満たされていることを確認します。




## <a name="30-days--powerful-quick-wins"></a>30 日間 — 強力で迅速な成功
タスクはすぐに実行できますので、ユーザーへの影響は少なくて済みます。

|||
|:-----|:-----|
|**領域**|**タスク**|
|ISO 27001 のガバナンスおよびコンプライアンス要件を理解します。|• 組織の ISO 27001:2013 評価を実施するために、[Microsoft コンプライアンス マネージャー](https://support.office.com/article/use-compliance-manager-to-help-meet-data-protection-and-regulatory-requirements-when-using-microsoft-cloud-services-429e686f-d8a6-455e-a2b6-3791d763f000)を [Microsoft Service Trust Portal](https://support.office.com/article/get-started-with-the-microsoft-service-trust-portal-f30e2353-0bd6-41ed-8347-eea1fb8d2662) (STP) 内で使用してコンプライアンス リスクを評価および管理します。14 の ISO 27001 グループごとに標準業務手順書 (SOP) を作成してください。
|機密データと資産を特定、分類、保護できるようにするための、情報分類、保持ポリシー、ツールの組織への展開を計画します。|• 分類ポリシーと [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-information-protection) アプリケーションを展開することにより、ユーザーが情報保護ポリシーと標準業務手順書 (SOP) に従って機密データを簡単に識別および分類できるようにします。組織の情報分類スキーマ (ポリシー) と共に、教育および展開計画を作成します。<br>• [Office 365 ラベル](https://support.office.com/article/overview-of-labels-af398293-c69d-465e-a249-d74561552d30)を組織に展開することで、ユーザーがレコードの保持および保護ポリシーをコンテンツに簡単に適用できるようにします。情報記録保持の法的要件に従って、組織のラベルを計画し、教育および展開計画も計画します。
|標準業務手順書 (SOP) の一環として監査および責任ポリシーを作成することにより、情報セキュリティに関連する記録が紛失、削除、改ざん、または不正アクセスされないようにします。|• [Office 365 の監査ログ記録](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)と[メールボックス監査](https://support.office.com/article/Enable-mailbox-auditing-in-Office-365-aaca8987-5b62-458b-9882-c28476a66918)を (すべての Exchange メールボックスに対して) 有効にして、潜在的な悪意のあるアクティビティがないか Office 365 を監視し、データ侵害のフォレンジック分析を可能にします。<br>• 通常のスケジュールで Office 365 テナントの監査ログを検索し、テナントの構成設定に加えられた変更を確認します。<br>• ユーザー アカウントの権限の昇格が発生した場合など、機密性の高いアクティビティに対して、Microsoft 365 セキュリティ/コンプライアンス センターの [Office 365 アラート ポリシー](https://support.office.com/article/alert-policies-in-the-office-365-security-compliance-center-8927b8b9-c5bc-45a8-a9f9-96c732e58264)を有効にします。<br>• Office 365 監査ログ データを長期間保存するには、[Office 365 マネージメント アクティビティ API リファレンス](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)を使用して、セキュリティ情報およびイベント管理 (SIEM) ツールと統合します。
|組織のための管理者ロールおよびセキュリティ ロールと共に、業務の分離に関連する適切な方針を定義します。|• 管理業務の分離を可能にするために、[Office 365 の管理者ロール](https://support.office.com/article/understanding-administrative-roles-52f29955-6a60-435f-aba9-eb69c898606a)を活用します。メモ: Office 365 の多くの管理者ロールには、Exchange Online、SharePoint Online、Skype for Business Online で対応するロールがあります。<br>• 一人の管理者が必要以上に大きいアクセス権を持たないようにするため、アクセス許可を分割します。|




## <a name="90-days--enhanced-protections"></a>90 日間 — 保護の強化 
タスクの計画と実装に少し時間がかかりますが、セキュリティ体制は大幅に向上します。 

|||
|:-----|:-----|
|**領域**|**タスク**|
|Microsoft 365 のセキュリティ機能を使用して環境へのアクセスを制御し、定義した標準業務手順書 (SOP) に従って組織の情報と資産を保護します。|• すべてのユーザー アカウントで多要素認証 (MFA) を有効にし、すべてのアプリで先進認証を有効にするなど、[ID とデバイス アクセス ポリシー](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations)を実装することによって、管理者とエンド ユーザーのアカウントを保護します。<br>• ユーザー アカウントの資格情報を管理および保護するための[強力なパスワード ポリシー](https://www.microsoft.com/research/publication/password-guidance/)を確立します。<br>• 機密データをメールで送信する際にエンド ユーザーが組織の SOP に準拠できるように [Office 365 Message Encryption (OME)](https://support.office.com/article/office-365-message-encryption-f87cb016-7876-4317-ae3c-9169b311ff8a) を設定します。<br>• 悪意のあるコードからの保護とデータ侵害の防止と対応のために、すべてのデスクトップに [Windows Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) (ATP) を展開します。<br>• 金融、医療など、個人を特定できる情報を含むドキュメントやメール内の 80 種類を超える一般的な機密データを特定、監視、[自動保護](https://docs.microsoft.com/office365/enterprise/apply-protection-to-personal-data-in-office-365)するための [Office 365 Data Loss Prevention (DLP) ポリシー](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)を構成、テスト、展開します。<br>• [ポリシー ヒント](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/policy-tips)を設定することで、ポリシーに抵触するメッセージを送信する前に、メールの送信者にポリシーの 1 つに違反している可能性があることを自動的に通知します。ポリシー ヒントを設定し、メッセージの作成時に可能性のあるポリシー違反についての情報を示す簡単なメモを、Outlook、Outlook on the web、デバイス用 OWA に表示するようにできます。<br>• [Office 365 Advanced Threat Protection (ATP)](https://support.office.com/article/office-365-advanced-threat-protection-e100fe7c-f2a1-4b7d-9e08-622330b83653) を実装し、フィッシング メールや悪意のあるリンクや添付ファイルを含む Office ドキュメントなど、最も一般的な攻撃ベクトルを防止します。|



## <a name="beyond-90-days--ongoing-security-data-governance-and-reporting"></a>90 日以降 – 継続的なセキュリティ、データ ガバナンス、およびレポート
保存中および送信中の個人データをセキュリティ保護し、データ侵害の検出および対応を行い、セキュリティ対策の定期的なテストを容易にします。これらは、これまでの作業に基づいて構築された重要なセキュリティ対策です。  


|||
|:-----|:-----|
|**領域**|**タスク**|
|Microsoft 365 の高度なデータ ガバナンス ツールと情報保護を使用して、個人データの継続的な管理プログラムを実装します。|• [Office 365 アドバンスト データ ガバナンス](https://docs.microsoft.com/office365/enterprise/apply-labels-to-personal-data-in-office-365)を使用して、Office 365  ラベルを自動的に適用することによって、ドキュメントおよびメール内の個人情報を特定します。<br>• [Microsoft Intune](https://docs.microsoft.com/intune/) を使用して、モバイル デバイスで保存およびアクセスされる機密データを組織全体で保護し、データに対して必ず準拠した会社のデバイスを使用するようにします。|
|Microsoft 365 および他のクラウド アプリケーション間で進行中のコンプライアンスを監視します。|• 標準業務手順書 (SOP) に対するパフォーマンスを評価するには、[Microsoft コンプライアンス マネージャー](https://support.office.com/article/use-compliance-manager-to-help-meet-data-protection-and-regulatory-requirements-when-using-microsoft-cloud-services-429e686f-d8a6-455e-a2b6-3791d763f000)を継続的に使用して、組織の情報セキュリティ ポリシーとその実装に対する定期的な ISO 27001:2013 評価を実行します。<br>• 情報セキュリティ管理システムを継続的に評価および監視します。<br>• [Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-configure) を使用して、高レベルのアクセス許可を持つすべてのユーザーおよびグループ (特権ユーザーまたは管理ユーザー) を制御し、定期的に評価します。<br>• [Office 365 で Privileged Access Management](https://docs.microsoft.com/office365/enterprise/privileged-access-management-in-office-365) を展開して構成することで、Office 365 の特権管理タスクに対して詳細なアクセス制御を提供します。有効になると、ユーザーは、細かく範囲指定され、期限のある承認ワークフローを通じて昇格タスクや特権タスクを完了するためにジャストインタイム アクセスを要求しなければならなくなります。<br>• 標準業務手順書 (SOP) の一環として、Office 365 監査ログを検索し、テナントの構成設定の変更、エンド ユーザーの権限昇格、および危険なユーザー アクティビティを確認します。<br>• [所有者以外のメールボックス アクセス](https://docs.microsoft.com/Exchange/policy-and-compliance/non-owner-mailbox-access-reports)を監査して、潜在的な情報漏洩を特定し、すべての Exchange Online メールボックスに対する所有者以外のアクセスを積極的に確認します。<br>• [Office 365 アラート ポリシー、データ損失防止レポート、Microsoft Cloud App Security](https://docs.microsoft.com/office365/enterprise/monitor-for-leaks-of-personal-data) を使用して、組織のクラウド アプリケーションの使用状況を監視し、ヒューリスティックおよびユーザー アクティビティに基づいて高度なアラート ポリシーを実装します。<br>• [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) を使用して、危険なアクティビティを追跡して、潜在的な悪意のある管理者を特定し、データ侵害を調査し、コンプライアンス要件が満たされていることを確認します。|







## <a name="learn-more"></a>詳細情報

Microsoft セキュリティ センター: [ISO/IEC 27001:2013 情報セキュリティ管理の標準](https://www.microsoft.com/TrustCenter/Compliance/ISO-IEC-27001)

[Microsoft Trust Center](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)


