# [Microsoft Defender for Endpoint](index.yml)

## [概要]()
### [Microsoft Defender for Endpoint とは](microsoft-defender-endpoint.md)
### [Defender for Endpoint プラン 1 とプラン 2を比較する](defender-endpoint-plan-1-2.md)
### [最小要件](minimum-requirements.md)
### [Microsoft Defender for Endpoint の新機能](whats-new-in-microsoft-defender-atp.md)
### [プレビュー機能](preview.md)
### [データの保存とプライバシー](data-storage-privacy.md)
### [Microsoft Defender セキュリティ センターの概要](use.md)
### [ポータルの概要](portal-overview.md)
### [Defender for Endpoint プラン 1]()
#### [概要](defender-endpoint-plan-1.md)
#### [セットアップと構成](mde-p1-setup-configuration.md)
#### [使用を開始する](mde-plan1-getting-started.md)
#### [メンテナンスと運用](mde-p1-maintenance-operations.md)
### [米国政府のお客様向けの Microsoft Defender for Endpoint](gov.md)
### [Windows 以外のプラットフォーム上の Microsoft Defender for Endpoint](non-windows.md)


## [機能を評価する](evaluation-lab.md)

## [展開を計画する](deployment-strategy.md)

## [展開ガイド]()
### [展開フェーズ](deployment-phases.md)
### [フェーズ 1: 準備](prepare-deployment.md)
### [フェーズ 2: 設定](production-deployment.md)
### [フェーズ 3: オンボード]()
#### [オンボーディングの概要](onboarding.md)
#### [展開リング](deployment-rings.md)
#### [Microsoft Endpoint Configuration Manager を使用したオンボーディング](onboarding-endpoint-configuration-manager.md)
#### [Microsoft エンドポイント マネージャーを使用したオンボーディング](onboarding-endpoint-manager.md)

## [移行ガイド](migration-guides.md)
### [Defender for Endpoint に移動する](switch-to-mde-overview.md)
#### [フェーズ 1: 準備](switch-to-mde-phase-1.md)
#### [フェーズ 2: セットアップ](switch-to-mde-phase-2.md)
#### [フェーズ 3: オンボード](switch-to-mde-phase-3.md)
#### [トラブルシューティング](switch-to-mde-troubleshooting.md)
### [移行後の Defender for Endpoint の管理](manage-mde-post-migration.md)
#### [Intune (推奨) を使用する](manage-mde-post-migration-intune.md)
#### [構成マネージャーを使用する](manage-mde-post-migration-configuration-manager.md)
#### [グループ ポリシーを使用する](manage-mde-post-migration-group-policy-objects.md)
#### [PowerShell、WMI、MPCmdRun.exe を使用する](manage-mde-post-migration-other-tools.md)
#### [サーバー移行シナリオ](server-migration.md)

## [デバイスの構成とオンボード]()
### [デバイスにオンボードして、Microsoft Defender for Endpoint 機能 を構成します](onboard-configure.md)


### [Windows および Windows Server 上の Microsoft Defender for Endpoint]()
#### [Windows エンドポイント用のオンボード ツールと各種方法](configure-endpoints.md)
#### [Windows デバイスと Windows サーバーのオンボード]()

##### [以前のバージョンの Windows をオンボードする](onboard-downlevel.md)


##### [Windows デバイスと Windows サーバーのオンボード]()
###### [Windows Server 2012 R2、2016、半期チャネル、2019、および 2022](configure-server-endpoints.md)をオンボードする
###### [ローカル スクリプトを使用した Windows デバイスのオンボード](configure-endpoints-script.md)
###### [グループ ポリシーを使用してデバイスをオンボードする](configure-endpoints-gp.md)
###### [Microsoft Endpoint Configuration Manager を使用した Windows デバイスのオンボード](configure-endpoints-sccm.md)
###### [モバイル デバイス管理ツールを使用した Windows デバイスのオンボード](configure-endpoints-mdm.md)
###### [非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード](configure-endpoints-vdi.md)
###### [Windows Virtual Desktop の Windows 10 マルチセッション デバイスのオンボード](onboard-windows-multi-session-device.md)




#### [Microsoft Defender for Cloudとの統合](azure-server-integration.md) 

#### [インターネット アクセスなしでデバイスをオンボードする](onboard-offline-machines.md)
#### [新しくオンボードされたデバイスで検出テストを実行する](run-detection-test.md)
#### [デバイスに対してシミュレートされた攻撃を実行する](attack-simulations.md)
#### [プロキシとインターネット接続の設定を構成する](configure-proxy-internet.md)
#### [オンボーディングまたはオフボーディングの通知ルールを作成する](onboarding-notification.md)

#### [アプリケーション ライセンス条項](mde-terms-windows.md)


### [他のオペレーティング システム上の Microsoft Defender for Endpoint]()
#### [Windows 以外のデバイスをオンボードする](configure-endpoints-non-windows.md)

#### [macOS 用 Microsoft Defender for Endpoint]()
##### [macOS 用 Microsoft Defender for Endpoint の概要](microsoft-defender-endpoint-mac.md)
##### [新機能](mac-whatsnew.md)

##### [展開]()
###### [Microsoft Intune ベースの展開](mac-install-with-intune.md)
###### [JAMF Pro ベースの展開]()
####### [Jamf Pro を使用した macOS 用 Microsoft Defender for Endpoint の展開](mac-install-with-jamf.md)
####### [Jamf Pro へのログイン](mac-install-jamfpro-login.md)
####### [デバイス グループを設定する](mac-jamfpro-device-groups.md)
####### [ポリシーを設定する](mac-jamfpro-policies.md)
####### [デバイスを登録する](mac-jamfpro-enroll-devices.md)

###### [別のモバイル デバイス管理 (MDM) システムを使用した展開](mac-install-with-other-mdm.md)
###### [手動展開](mac-install-manually.md)
##### [更新](mac-updates.md)

##### [構成]()
###### [除外を構成および検証する](mac-exclusions.md)
###### [環境設定](mac-preferences.md)
###### [望ましくない可能性のあるアプリケーションを検出してブロックする](mac-pua.md)
###### [デバイス コントロール]()
####### [デバイス コントロールの概要](mac-device-control-overview.md)
####### [JAMF の例](mac-device-control-jamf.md)
####### [Intune の例](mac-device-control-intune.md)
###### [スキャンのスケジュール](mac-schedule-scan.md)

##### [トラブルシューティング]()
###### [インストールに関する問題のトラブルシューティング](mac-support-install.md)
###### [パフォーマンスに関する問題のトラブルシューティング](mac-support-perf.md)
###### [クラウド接続に関する問題のトラブルシューティング](troubleshoot-cloud-connect-mdemac.md)
###### [カーネル拡張に関する問題のトラブルシューティング](mac-support-kext.md)
###### [ライセンスに関する問題のトラブルシューティング](mac-support-license.md)

##### [プライバシー](mac-privacy.md)
##### [リソース](mac-resources.md)
##### [アプリケーション ライセンス条項](mde-terms-mac.md)

#### [Linux 用 Microsoft Defender for Endpoint]()
##### [Linux 用 Microsoft Defender for Endpoint の概要](microsoft-defender-endpoint-linux.md)
##### [新機能](linux-whatsnew.md)
##### [展開]()
###### [手動展開](linux-install-manually.md)
###### [Puppet ベースの展開](linux-install-with-puppet.md)
###### [Ansible ベースの展開](linux-install-with-ansible.md)
###### [Chef を使用して Linux 用 Microsoft Defender for Endpoint を展開する](linux-deploy-defender-for-endpoint-with-chef.md)

##### [更新](linux-updates.md)

##### [構成]()
###### [除外を構成および検証する](linux-exclusions.md)
###### [静的プロキシの構成](linux-static-proxy-configuration.md)
###### [環境設定](linux-preferences.md)
###### [望ましくない可能性のあるアプリケーションを検出してブロックする](linux-pua.md)
###### [Linux 用 Microsoft Defender for Endpoint でスキャンをスケジュールする](linux-schedule-scan-atp.md)
###### [Microsoft Defender for Endpoint (Linux) の更新をスケジュールする](linux-update-MDE-Linux.md)


##### [トラブルシューティング]()
###### [インストールに関する問題のトラブルシューティング](linux-support-install.md)
###### [エージェントの正常性に関する問題の調査](health-status.md)
###### [クラウド接続に関する問題のトラブルシューティング](linux-support-connectivity.md)
###### [RHEL6 のインストールに関する問題のトラブルシューティング](linux-support-rhel.md)
###### [パフォーマンスに関する問題のトラブルシューティング](linux-support-perf.md)
###### [欠落しているイベントに関する問題のトラブルシューティング](linux-support-events.md)

##### [プライバシー](linux-privacy.md)
##### [リソース](linux-resources.md)

#### [モバイル脅威防御]()
##### [モバイル脅威防御の概要](mtd.md)

##### [Android 用 Microsoft Defender for Endpoint]()
###### [Android 用 Microsoft Defender for Endpoint の概要](microsoft-defender-endpoint-android.md)
###### [新機能](android-whatsnew.md)

###### [展開]()
####### [Microsoft Intune を使用した Android 用 Microsoft Defender for Endpoint の展開](android-intune.md)

###### [構成]()
####### [Android 機能用に Microsoft Defender for Endpoint を構成する](android-configure.md)
####### [アプリ保護ポリシーを使用して、Microsoft Defender for Endpoint リスク シグナルを構成する](android-configure-mam.md)

###### [プライバシー]()
####### [Android 用 Microsoft Defender for Endpoint - プライバシー情報](android-privacy.md)

###### [トラブルシューティング]()
####### [問題のトラブルシューティング](android-support-signin.md)

##### [iOS 用 Microsoft Defender for Endpoint API]()
###### [iOS 用 Microsoft Defender for Endpoint の概要](microsoft-defender-endpoint-ios.md)
###### [新機能](ios-whatsnew.md)

###### [展開]()
####### [Intune を介した iOS 用 Microsoft Defender for Endpoint の展開](ios-install.md)
####### [未登録のデバイスに対する iOS 用 Microsoft Defender for Endpoint の展開](ios-install-unmanaged.md)

###### [iOS 機能の構成](ios-configure-features.md)

###### [FAQ およびトラブルシューティング](ios-troubleshoot.md)

###### [プライバシー](ios-privacy.md)

##### [Microsoft Defender for Endpoint アプリケーション ライセンス条項](mde-terms-mobile.md) 

### [Microsoft エンドポイント マネージャーを使用してデバイス上の Microsoft Defender for Endpoint の構成設定を管理する](security-config-management.md)

### [オンボーディングに関する問題のトラブルシューティング]()
#### [オンボーディング中の問題のトラブルシューティング](troubleshoot-onboarding.md)
#### [サブスクリプションとポータル アクセスの問題のトラブルシューティング](troubleshoot-onboarding-error-messages.md)
#### [セキュリティ構成管理のオンボーディングに関する問題のトラブルシューティング](troubleshoot-security-config-mgt.md)





### [ポータル設定を構成する]()
#### [環境設定](preferences-setup.md)
#### [全般]()
##### [データの保管場所を確認し、データ保持設定を更新する](data-retention-settings.md)
##### [アラート通知を構成する](configure-email-notifications.md)
##### [脆弱性メール通知を構成する](configure-vulnerability-email-notifications.md)
##### [高度な機能を構成する](advanced-features.md)

#### [アクセス許可]()
##### [基本的なアクセス許可を使用してポータルにアクセスする](basic-permissions.md)
##### [RBAC を使用してポータル アクセスを管理する](rbac.md)
###### [役割の作成と管理](user-roles.md)
###### [デバイス グループの作成と管理](machine-groups.md)
###### [デバイス タグの作成と管理](machine-tags.md)

#### [ルール]()
##### [抑制ルールの管理](manage-suppression-rules.md)
##### [インジケーターの作成](manage-indicators.md)
###### [ファイルのインジケーターを作成 ](indicator-file.md)
###### [IP および URL/ドメインのインジケーターを作成](indicator-ip-domain.md)
###### [証明書のインジケーターを作成 ](indicator-certificates.md)
###### [インジケーターの管理](indicator-manage.md)
##### [自動化ファイルのアップロードを管理する](manage-automation-file-uploads.md)
##### [自動化フォルダーの除外を管理する](manage-automation-folder-exclusions.md)

#### [デバイスの管理]()
##### [デバイスのオンボーディング](onboard-configure.md)
##### [デバイスのオフボーディング](offboard-machines.md)
##### [デバイスが正しく構成されていることを確認する](configure-machines.md)
##### [デバイスのオンボーディングを監視および強化する](configure-machines-onboarding.md)

#### [Microsoft Defender セキュリティ センターのタイム ゾーン設定を構成する](time-settings.md)

## [脅威の検出とエンドポイントの保護]()
### [脅威と脆弱性の管理]()
#### [概要](next-gen-threat-and-vuln-mgt.md)
#### [はじめに]()
##### [アクセス許可と前提条件](tvm-prerequisites.md)
##### [サポート対象オペレーティング システムのプラットフォームと機能](tvm-supported-os.md)
##### [デバイス値の割り当て](tvm-assign-device-value.md)
#### [セキュリティ体制にアクセス]()
##### [ダッシュボード インサイト](tvm-dashboard-insights.md)
##### [暴露スコア](tvm-exposure-score.md)
##### [デバイス向けの Microsoft セキュア スコア](tvm-microsoft-secure-score-devices.md)
#### [セキュリティの状態の改善とリスクの軽減]()
##### [セキュリティ上の推奨事項に対処する](tvm-security-recommendation.md)
##### [脆弱性を修復する](tvm-remediation.md)
##### [セキュリティ上の推奨事項の例外](tvm-exception.md)
##### [サポート終了ソフトウェアの計画](tvm-end-of-support-software.md)
##### [ゼロデイ脆弱性を軽減する](tvm-zero-day-vulnerabilities.md)
#### [デバイスの脆弱性を理解する]()
##### [ソフトウェア インベントリ](tvm-software-inventory.md)
##### [組織の脆弱性](tvm-weaknesses.md)
##### [イベントのタイムライン](threat-and-vuln-mgt-event-timeline.md)
##### [脆弱なデバイスのレポート](tvm-vulnerable-devices-report.md)
##### [露出したデバイスの追求](tvm-hunt-exposed-devices.md)

### [デバイス検出]()
#### [デバイス検出の概要](device-discovery.md)
#### [デバイス検出の構成](configure-device-discovery.md)
#### [デバイス検出に関する FAQ](device-discovery-faq.md)

### [ネットワークデバイス](network-devices.md)

### [Microsoft Defender for Endpoint でのホスト ファイアウォール レポート](host-firewall-reporting.md)

### [攻撃面の減少]()
#### [攻撃面の減少の概要](overview-attack-surface-reduction.md)
#### [攻撃面の減少機能を構成する](configure-attack-surface-reduction.md)
#### [攻撃面の減少ルールの詳細](attack-surface-reduction.md)
#### [攻撃面の減少ルール](attack-surface-reduction-rules.md)
#### [攻撃面の減少 (ASR) ルールを展開する](attack-surface-reduction-rules-deployment.md)
##### [ASR ルール 展開フェーズ 1 - 計画](attack-surface-reduction-rules-deployment-phase-1.md)
##### [ASR ルール 展開フェーズ 2 - テスト](attack-surface-reduction-rules-deployment-phase-2.md)
##### [ASR ルール 展開フェーズ 3 - 実装](attack-surface-reduction-rules-deployment-phase-3.md)
##### [ASR ルール 展開フェーズ 4 - 運用化](attack-surface-reduction-rules-deployment-phase-4.md)
#### [攻撃面の減少ルールを評価する](evaluate-attack-surface-reduction.md)
#### [攻撃面の減少ルールを有効にする](enable-attack-surface-reduction.md)
#### [攻撃面の減少ルールをカスタマイズする](customize-attack-surface-reduction.md)
#### [攻撃面の減少の FAQ](attack-surface-reduction-faq.yml)
#### [攻撃面の減少イベントを表示する](event-views.md)
#### [攻撃面の減少に監査モードを使用する](audit-windows-defender.md)

### 次世代の保護
#### [次世代保護の概要](next-generation-protection.md)
##### [Microsoft Defender ウイルス対策の概要](microsoft-defender-antivirus-windows.md)
##### [ベストな組み合わせ: Microsoft Defender Antivirus および Microsoft Defender for Endpoint](why-use-microsoft-defender-antivirus.md)
##### [ベストな組み合わせ: Microsoft Defender ウイルス対策と Office 365](office-365-microsoft-defender-antivirus.md)
#### [Microsoft Defender ウイルス対策を評価する](evaluate-microsoft-defender-antivirus.md)
#### [Microsoft Defender ウイルス対策機能を構成する](configure-microsoft-defender-antivirus-features.md)
#### [クラウド保護と Microsoft Defender ウイルス対策](cloud-protection-microsoft-defender-antivirus.md)
##### [クラウド保護を有効にする理由](why-cloud-protection-should-be-on-mdav.md)
##### [クラウド保護を有効にする](enable-cloud-protection-microsoft-defender-antivirus.md)
##### [クラウド保護レベルを指定する](specify-cloud-protection-level-microsoft-defender-antivirus.md)
##### [クラウド保護とサンプルの送信](cloud-protection-microsoft-antivirus-sample-submission.md)
#### [Microsoft Defender ウイルス対策 ネットワーク接続を構成および検証する](configure-network-connections-microsoft-defender-antivirus.md)
#### [改ざん防止機能を使用してセキュリティ設定を保護する](prevent-changes-to-security-settings-with-tamper-protection.md)
#### [事前ブロックを有効にする](configure-block-at-first-sight-microsoft-defender-antivirus.md)
#### [クラウド ブロックのタイムアウト期間の構成](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
#### [行動、ヒューリスティック、リアルタイム保護を構成する](configure-protection-features-microsoft-defender-antivirus.md)
#### [望ましくない可能性のあるアプリケーションを検出してブロックする](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md)
#### [グループ ポリシーで Microsoft Defender ウイルス対策を常時保護を有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md)
#### [Microsoft Defender ウイルス対策検出の修復を構成する](configure-remediation-microsoft-defender-antivirus.md)
#### [Microsoft Defender ウイルス対策スキャンを構成する](schedule-antivirus-scans.md)
##### [グループ ポリシーを使用しスキャンをスケジュールする](schedule-antivirus-scans-group-policy.md)
##### [PowerShell を使用してスキャンをスケジュールする](schedule-antivirus-scans-powershell.md)
##### [WMI を使用してスキャンをスケジュールする](schedule-antivirus-scans-wmi.md)
#### [Microsoft Defender ウイルス対策で限定された定期的なスキャンを使用する](limited-periodic-scanning-microsoft-defender-antivirus.md)
#### [Microsoft Defender ウイルス対策のパフォーマンスの調整](tune-performance-defender-antivirus.md)
#### [他のセキュリティ製品との互換性](microsoft-defender-antivirus-compatibility.md)

#### [ウイルス対策ソフトウェアとマルウェア対策の更新プログラムを取得する](manage-updates-baselines-microsoft-defender-antivirus.md)
##### [Microsoft Defender ウイルス対策更新プログラムのソースを管理する](manage-protection-updates-microsoft-defender-antivirus.md)
##### [保護更新プログラムをダウンロードして適用するスケジュールを管理する](manage-protection-update-schedule-microsoft-defender-antivirus.md)
##### [Microsoft Defender の更新プログラムの段階的な展開プロセスを管理する](manage-gradual-rollout.md)
##### [Microsoft Defender の更新プログラムの段階的な展開プロセスを構成する](configure-updates.md)
##### [Microsoft Defender ウイルス対策の更新プログラムを管理し、古くなったエンドポイントをスキャンする](manage-outdated-endpoints-microsoft-defender-antivirus.md)
##### [イベントベースの強制更新プログラムを管理する](manage-event-based-updates-microsoft-defender-antivirus.md)
##### [モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)

#### [組織の Microsoft Defender ウイルス対策を管理する](configuration-management-reference-microsoft-defender-antivirus.md)
##### [Microsoft エンドポイント マネージャーを使用して Microsoft Defender ウイルス対策を管理する](use-intune-config-manager-microsoft-defender-antivirus.md)
##### [グループ ポリシー設定を使用して Microsoft Defender ウイルス対策を管理する](use-group-policy-microsoft-defender-antivirus.md)
##### [PowerShell コマンドレットを使った Microsoft Defender ウイルス対策の管理](use-powershell-cmdlets-microsoft-defender-antivirus.md)
##### [Microsoft Defender ウイルス対策を管理するために Windows Management Instrumentation (WMI) を使用する](use-wmi-microsoft-defender-antivirus.md)
##### [mpcmdrun.exe ツールを使用して Microsoft Defender ウイルス対策を管理する](command-line-arguments-microsoft-defender-antivirus.md)
##### [エンドポイントに表示される通知を構成する](configure-notifications-microsoft-defender-antivirus.md)
##### [ユーザーが Microsoft Defender ウイルス対策のポリシー設定をローカルで変更できるかどうかを指定する](configure-local-policy-overrides-microsoft-defender-antivirus.md)
##### [ユーザーが Microsoft Defender ウイルス対策のユーザー インターフェイスを表示できるかどうか、または操作できるかどうかを指定する](prevent-end-user-interaction-microsoft-defender-antivirus.md)

#### [Microsoft Defender ウイルス対策を展開してレポートする](deploy-manage-report-microsoft-defender-antivirus.md)
##### [Microsoft Defender ウイルス対策を展開して有効にする](deploy-microsoft-defender-antivirus.md)
##### [仮想デスクトップ インフラストラクチャ (VDI) 環境での Microsoft Defender ウイルス対策の展開ガイド](deployment-vdi-microsoft-defender-antivirus.md)
##### [Microsoft Defender ウイルス対策のレポート](report-monitor-microsoft-defender-antivirus.md)

#### [スキャンと修復](review-scan-results-microsoft-defender-antivirus.md)
##### [オンデマンドの Microsoft Defender ウイルス対策スキャンを構成して実行する](run-scan-microsoft-defender-antivirus.md)
##### [Microsoft Defender オフライン スキャンの結果を実行してレビューする](microsoft-defender-offline.md)
##### [Microsoft Defender ウイルス対策スキャン オプションを構成する](configure-advanced-scan-types-microsoft-defender-antivirus.md)
##### [Microsoft Defender ウイルス対策で検疫済みファイルを復元する](restore-quarantined-files-microsoft-defender-antivirus.md)

#### [Microsoft Defender ウイルス対策の除外](configure-exclusions-microsoft-defender-antivirus.md)
##### [ファイル拡張子とフォルダーの場所に基づく除外](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
##### [プロセスによって開かれたファイルの除外](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
##### [Windows Server の除外](configure-server-exclusions-microsoft-defender-antivirus.md)
##### [回避するべき一般的なミス](common-exclusion-mistakes-microsoft-defender-antivirus.md)

#### Microsoft Defender ウイルス対策のトラブルシューティング
##### [更新プログラムのコンプライアンスでの Microsoft Defender ウイルス対策レポートのトラブルシューティング](troubleshoot-reporting.md)
##### [パフォーマンスに関する問題のトラブルシューティング](troubleshoot-performance-issues.md)
##### [Microsoft Defender ウイルス対策ソフトウェアの問題をトラブルシューティングするため、イベント ログとエラー コードをレビューする](troubleshoot-microsoft-defender-antivirus.md)
##### [サード パーティのソリューションからの移行中に Microsoft Defender ウイルスのトラブルシューティングを行う](troubleshoot-microsoft-defender-antivirus-when-migrating.md)

#### [エクスプロイト保護]()
##### [エクスプロイトからデバイスを保護する](exploit-protection.md)
##### [エクスプロイト保護の評価](evaluate-exploit-protection.md)
##### [エクスプロイト保護を有効にする](enable-exploit-protection.md)
##### [エクスプロイト保護をカスタマイズする](customize-exploit-protection.md)
##### [エクスプロイト保護構成のインポート、エクスポート、展開](import-export-exploit-protection-emet-xml.md)
##### [エクスプロイト保護のリファレンス](exploit-protection-reference.md)

#### [ネットワーク保護]()
##### [ネットワークを保護する](network-protection.md)
##### [ネットワーク保護を評価する](evaluate-network-protection.md)
##### [ネットワーク保護を有効にする](enable-network-protection.md)

#### [Web 保護]()
##### [Web 保護の概要](web-protection-overview.md)
##### [Web の脅威に対する保護]()
###### [Web の脅威に対する保護の概要](web-threat-protection.md)
###### [Web セキュリティの監視](web-protection-monitoring.md)
###### [Web の脅威への対応](web-protection-response.md)
##### [Web コンテンツ フィルタリング](web-content-filtering.md)

#### [制御されたフォルダー アクセス]()
##### [フォルダーの保護](controlled-folders.md)
##### [制御されたフォルダー アクセスを評価する](evaluate-controlled-folder-access.md)
##### [制御されたフォルダー アクセスを有効にする](enable-controlled-folders.md)
##### [制御されたフォルダー アクセスをカスタマイズする](customize-controlled-folders.md)

#### [デバイス コントロール]()
##### [リムーバブル記憶域の保護](device-control-removable-storage-protection.md)
##### [リムーバブル記憶域のアクセス制御](device-control-removable-storage-access-control.md)
##### [デバイスのインストール](mde-device-control-device-installation.md)
##### [デバイス制御のプリンター保護](printer-protection.md)
##### [デバイス コントロールのレポート](device-control-report.md)

#### [動作ブロックと封じ込め]()
##### [動作ブロックと封じ込め](behavioral-blocking-containment.md)
##### [クライアントの動作ブロック](client-behavioral-blocking.md)
##### [フィードバック ループのブロック](feedback-loop-blocking.md)


### [Microsoft Defender for Endpoint での誤検出/検出漏れに対処する](defender-endpoint-false-positives-negatives.md)


### [デバイス構成の管理]()

#### [セキュリティ ベースラインへの準拠を強化する](configure-machines-security-baseline.md)
#### [攻撃面の減少ルールの展開と検出を最適化する](configure-machines-asr.md)

## [脅威の調査と対応]()
### [エンドポイントでの検出と対応]()
#### [エンドポイントでの検出と対応の概要](overview-endpoint-detection-response.md)
#### [セキュリティ運用ダッシュボード](security-operations-dashboard.md)
#### [インシデント キュー]()
##### [インシデント キューを表示および整理する](view-incidents-queue.md)
##### [インシデントの管理](manage-incidents.md)
##### [インシデントの調査](investigate-incidents.md)

#### [アラート キュー]()
##### [Microsoft 365 Defender のアラート キュー](alerts-queue-endpoint-detection-response.md)
##### [アラート キューを表示および整理する](alerts-queue.md)
##### [アラートの確認](review-alerts.md)
##### [アラートの管理](manage-alerts.md)
##### [アラートの調査](investigate-alerts.md)
##### [ファイルの調査](investigate-files.md)
##### [デバイスの調査](investigate-machines.md)
##### [IP アドレスの調査](investigate-ip.md)
##### [ドメインの調査](investigate-domain.md)
###### [転送プロキシの背後で発生する接続イベントの調査](investigate-behind-proxy.md)
##### [ユーザー アカウントの調査](investigate-user.md)

#### [デバイスの一覧]()
##### [デバイスの一覧を表示および整理する](machines-view-overview.md)
##### [デバイス タイムライン イベント フラグ](device-timeline-event-flag.md)
##### [デバイス グループとタグの管理](machine-tags.md)

#### [対応措置を講じる]()
##### [デバイスの対応措置を講じる]()
###### [デバイスの対応措置](respond-machine-alerts.md)
###### [タグの管理](respond-machine-alerts.md#manage-tags)
###### [自動調査の開始](respond-machine-alerts.md#initiate-automated-investigation)
###### [ライブ応答セッションの開始](respond-machine-alerts.md#initiate-live-response-session)
###### [調査パッケージの収集](respond-machine-alerts.md#collect-investigation-package-from-devices)
###### [ウイルス対策スキャンを実行する](respond-machine-alerts.md#run-microsoft-defender-antivirus-scan-on-devices)
###### [アプリの実行を制限する](respond-machine-alerts.md#restrict-app-execution)
###### [ネットワークからデバイスを分離する](respond-machine-alerts.md#isolate-devices-from-the-network)
###### [脅威のエキスパートに相談する](respond-machine-alerts.md#consult-a-threat-expert)
###### [アクション センターでアクティビティの詳細を確認する](respond-machine-alerts.md#check-activity-details-in-action-center)

##### [ファイルの対応措置を講じる]()
###### [ファイルの対応措置](respond-file-alerts.md)
###### [ネットワーク内のファイルを停止して検疫する](respond-file-alerts.md#stop-and-quarantine-files-in-your-network)
###### [検疫からファイルを復元する](respond-file-alerts.md#restore-file-from-quarantine)
###### [ファイルをブロックまたは許可するインジケーターを追加する](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
###### [脅威のエキスパートに相談する](respond-file-alerts.md#consult-a-threat-expert)
###### [アクション センターでアクティビティの詳細を確認する](respond-file-alerts.md#check-activity-details-in-action-center)
###### [ファイルをダウンロードまたは収集する](respond-file-alerts.md#download-or-collect-file)
###### [詳細分析](respond-file-alerts.md#deep-analysis)

#### [修復アクションを表示および承認する](manage-auto-investigation.md)
##### [自動調査の詳細と結果を表示する](auto-investigation-action-center.md)

#### [ライブ応答を使用してエンティティを調査する]()
##### [デバイス上のエンティティを調査する](live-response.md)
##### [ライブ応答コマンドの例](live-response-command-examples.md)

#### [秘密度ラベルを使用してインシデント対応に優先順位を付ける](information-protection-investigation.md)

#### [レポート]()
##### [Power BI - API の使用方法 - サンプル](api-power-bi.md)
##### [脅威に対する保護のレポート](threat-protection-reports.md)
#### [デバイスの正常性とコンプライアンスのレポート](machine-reports.md)

### [高度な追求]()
#### [高度な追求の概要](advanced-hunting-overview.md)
#### [スキーマを理解する](advanced-hunting-schema-reference.md)
#### [DeviceAlertEvents](advanced-hunting-devicealertevents-table.md)

### [脅威の分析の概要](threat-analytics.md)
#### [アナリスト レポートを読む](threat-analytics-analyst-reports.md)

### [ブロック モードの EDR](edr-in-block-mode.md)

### [自動調査と応答 (AIR) ]()
#### [AIR の概要](automated-investigations.md)
#### [AIR の自動化レベル](automation-levels.md)
#### [AIR 機能の構成](configure-automated-investigations-remediation.md)

### [Microsoft 脅威エキスパート]()
#### [Microsoft 脅威エキスパートの概要](microsoft-threat-experts.md)
#### [Microsoft 脅威エキスパートの機能を構成および管理する](configure-microsoft-threat-experts.md)



## 参照
### [脅威インテリジェンスの概念を理解する](threat-indicator-concepts.md)
### [他の Microsoft ソリューションとの統合を構成する]()
#### [条件付きアクセスを構成する](configure-conditional-access.md)
#### [Microsoft Defender for Cloud Apps を統合のために構成する](microsoft-cloud-app-security-config.md)
### [管理と API]()
#### [管理と API の概要](management-apis.md)
#### [API リリースノート](api-release-notes.md)
#### [Microsoft Defender for Endpoint API]()
##### [概要]()
###### [Microsoft Defender for Endpoint API ライセンスと条件](api-terms-of-use.md)
###### [Microsoft Defender for Endpoint API にアクセスする](apis-intro.md)
###### [Hello World](api-hello-world.md)
###### [アプリケーション コンテキストでアクセスする](exposed-apis-create-app-webapp.md)
###### [ユーザー コンテキストでアクセスする](exposed-apis-create-app-nativeapp.md)



##### [Microsoft Defender for Endpoint API スキーマ]()
###### [サポート対象 Microsoft Defender for Endpoint API](exposed-apis-list.md)
###### [一般的な REST API エラー コード](common-errors.md)
###### [高度な追求](run-advanced-query-api.md)

###### [アラート]()
####### [アラート メソッドとプロパティ](alerts.md)
####### [アラートの一覧表示](get-alerts.md)
####### [アラートの作成](create-alert-by-reference.md)
####### [アラートのバッチ更新](batch-update-alerts.md)
####### [アラートの更新](update-alert.md)
####### [ID でアラート情報を取得する](get-alert-info-by-id.md)
####### [アラート関連のドメイン情報を取得する](get-alert-related-domain-info.md)
####### [アラート関連のファイル情報を取得する](get-alert-related-files-info.md)
####### [アラート関連の IP 情報を取得する](get-alert-related-ip-info.md)
####### [アラート関連のデバイス情報を取得する](get-alert-related-machine-info.md)
####### [アラート関連のユーザー情報を取得する](get-alert-related-user-info.md)


###### [脆弱性と安全な構成の評価]()
####### [評価方法とプロパティのエクスポート](get-assessment-methods-properties.md)
####### [安全な構成評価のエクスポート](get-assessment-secure-config.md)
####### [ソフトウェア在庫評価のエクスポート](get-assessment-software-inventory.md)
####### [ソフトウェアの脆弱性評価のエクスポート](get-assessment-software-vulnerabilities.md)

###### [自動調査]()
####### [調査メソッドとプロパティ](investigation.md)
####### [調査の一覧表示](get-investigation-collection.md)
####### [調査の取得](get-investigation-object.md)
####### [調査の開始](initiate-autoir-investigation.md)

###### [ドメイン]()
####### [ドメイン関連のアラートを取得する](get-domain-related-alerts.md)
####### [ドメイン関連のマシンを取得する](get-domain-related-machines.md)
####### [ドメイン統計を取得する](get-domain-statistics.md)

###### [ファイル]()
####### [ファイル メソッドとプロパティ](files.md)
####### [ファイル情報を取得する](get-file-information.md)
####### [ファイル関連のアラートを取得する](get-file-related-alerts.md)
####### [ファイル関連のマシンを取得する](get-file-related-machines.md)
####### [ファイル統計を取得する](get-file-statistics.md)

###### [インジケーター]()
####### [インジケーター メソッドとプロパティ](ti-indicator.md)
####### [インジケーターの一覧表示](get-ti-indicators-collection.md)
####### [インジケーターの送信](post-ti-indicator.md)
####### [インジケーターのインポート](import-ti-indicators.md)
####### [インジケーターの削除](delete-ti-indicator-by-id.md)

###### [IP]()
####### [IP 関連のアラートを取得する](get-ip-related-alerts.md)
####### [IP 統計を取得する](get-ip-statistics.md)


###### [マシン]()
####### [マシン メソッドとプロパティ](machine.md)
####### [マシンの一覧表示](get-machines.md)
####### [ID でマシンを取得する](get-machine-by-id.md)
####### [ユーザーのマシン ログオンを取得する](get-machine-log-on-users.md)
####### [マシン関連のアラートを取得する](get-machine-related-alerts.md)
####### [インストールされたソフトウェアを取得する](get-installed-software.md)
####### [検出された脆弱性を取得する](get-discovered-vulnerabilities.md)
####### [セキュリティ上の推奨事項を取得する](get-security-recommendations.md)
####### [マシン タグの追加または削除](add-or-remove-machine-tags.md)
####### [IP でマシンを検出する](find-machines-by-ip.md)
####### [タグでマシンを検出する](find-machines-by-tag.md)
####### [不足している KB を取得する](get-missing-kbs-machine.md)
####### [デバイス値の設定](set-device-value.md)
####### [コンピューターの更新](update-machine-method.md)



###### [マシン アクション]()
####### [マシン アクション メソッドとプロパティ](machineaction.md)
####### [マシン アクションの一覧表示](get-machineactions-collection.md)
####### [マシン アクションの取得](get-machineaction-object.md)
####### [調査パッケージの収集](collect-investigation-package.md)
####### [調査パッケージ SAS URI の取得](get-package-sas-uri.md)
####### [ライブ応答結果の取得](get-live-response-result.md)
####### [マシンの隔離](isolate-machine.md)
####### [マシンを隔離から解放する](unisolate-machine.md)
####### [アプリの実行を制限する](restrict-code-execution.md)
####### [アプリの制限を削除する](unrestrict-code-execution.md)
####### [ウイルス対策スキャンを実行する](run-av-scan.md)
####### [ライブ応答を実行する](run-live-response.md)
####### [マシンのオフボード](offboard-machine-api.md)
####### [ファイルの停止と検疫](stop-and-quarantine-file.md)
####### [マシン アクションのキャンセル](cancel-machine-action.md)

###### [推奨事項]()
####### [推奨メソッドとプロパティ](recommendation.md)
####### [すべての推奨事項を一覧表示する](get-all-recommendations.md)
####### [ID による推奨事項の取得](get-recommendation-by-id.md)
####### [ソフトウェアによる推奨事項の取得](list-recommendation-software.md)
####### [推奨事項によるマシンの一覧表示](get-recommendation-machines.md)
####### [推奨事項による脆弱性の一覧表示](get-recommendation-vulnerabilities.md)

###### [修復アクティビティ]()
####### [修復アクティビティのメソッドとプロパティ](get-remediation-methods-properties.md)
####### [ID による 1 つの修復アクティビティを取得する](get-remediation-one-activity.md)
####### [すべての修復作業を一覧表示する](get-remediation-all-activities.md)
####### [1 つの修復アクティビティの暴露デバイスを一覧表示する](get-remediation-exposed-devices-activities.md)

###### [スコア]()
####### [スコア メソッドとプロパティ](score.md)
####### [マシン グループごとの暴露スコアを一覧表示する](get-machine-group-exposure-score.md)
####### [暴露スコアを取得する](get-exposure-score.md)
####### [デバイスのセキュア スコアを取得する](get-device-secure-score.md)

###### [ソフトウェア]()
####### [ソフトウェア メソッドとプロパティ](software.md)
####### [ソフトウェアの一覧表示](get-software.md)
####### [ID でソフトウェアを取得する](get-software-by-id.md)
####### [ソフトウェア バージョンの配布を一覧表示する](get-software-ver-distribution.md)
####### [ソフトウェアによるマシンの一覧表示](get-machines-by-software.md)
####### [ソフトウェアによる脆弱性の一覧表示](get-vuln-by-software.md)
####### [不足している KB を取得する](get-missing-kbs-software.md)

###### [ユーザー]()
####### [ユーザー メソッド](user.md)
####### [ユーザー関連のアラートを取得する](get-user-related-alerts.md)
####### [ユーザー関連のマシンを取得する](get-user-related-machines.md)

###### [脆弱性]()
####### [脆弱性メソッドとプロパティ](vulnerability.md)
####### [脆弱性の一覧表示](get-all-vulnerabilities.md)
####### [マシンとソフトウェアによる脆弱性の一覧表示](get-all-vulnerabilities-by-machines.md)
####### [ID による脆弱性の取得](get-vulnerability-by-id.md)
####### [脆弱性によるマシンの一覧表示](get-machines-by-vulnerability.md)

##### [API の使用方法 - サンプル]()
###### [Power Automate](api-microsoft-flow.md)
###### [Power BI](api-power-bi.md)
###### [Python を使用した高度な追求](run-advanced-query-sample-python.md)
###### [PowerShell を使用した高度な追求](run-advanced-query-sample-powershell.md)
###### [OData クエリの使用](exposed-apis-odata-samples.md)


#### [生データ ストリーミング API]()
##### [生データ ストリーミング](raw-data-export.md)
##### [高度な追求イベントを Azure イベント ハブにストリーミングする](raw-data-export-event-hub.md)
##### [高度な追求イベントをストレージ アカウントにストリーミングする](raw-data-export-storage.md)

#### [SIEM 統合]()
##### [Microsoft Defender for Endpoint を使用して SIEM ツールを統合する](configure-siem.md)
##### [Microsoft Defender for Endpoint の検出フィールド](api-portal-mapping.md)
##### [SIEM REST API を使用した検出のプル](pull-alerts-using-rest-api.md)
##### [SIEM ツール統合に関する問題のトラブルシューティング](troubleshoot-siem.md)

#### [パートナーと API]()
##### [パートナー アプリケーション](partner-applications.md)
##### [接続されたアプリケーション](connected-applications.md)
##### [API エクスプローラー](api-explorer.md)

#### [ロール ベースのアクセス制御]()
##### [RBAC を使用してポータル アクセスを管理する](rbac.md)
##### [役割の作成と管理](user-roles.md)
##### [デバイス グループの作成と管理]()
###### [デバイス グループの使用](machine-groups.md)
###### [デバイス タグの作成と管理](machine-tags.md)







### [マネージド セキュリティ サービス プロバイダー (MSSP) の統合]()
#### [マネージド セキュリティ サービス プロバイダーの統合を構成する](configure-mssp-support.md)
#### [サポート対象マネージド セキュリティ サービス プロバイダー](mssp-list.md)
#### [ポータルへの MSSP アクセスを許可する](grant-mssp-access.md)
#### [MSSP カスタマー ポータルにアクセスする](access-mssp-portal.md)
#### [アラート通知を構成する](configure-mssp-notifications.md)
#### [パートナー アプリケーションへのアクセスを取得する](exposed-apis-create-app-partners.md)
#### [顧客テナントからアラートを取得する](fetch-alerts-mssp.md)
#### [マネージド セキュリティ サービス プロバイダーの機会](mssp-support.md)
### [パートナー統合シナリオ]()
#### [テクニカル パートナーの機会](partner-integration.md)
#### [Microsoft Defender for Endpoint パートナーになる](get-started-partner-integration.md)
### [統合]()
#### [Microsoft Defender for Endpoint 統合](threat-protection-integration.md)
#### [条件付きアクセスでユーザー、データ、デバイスを保護する](conditional-access.md)
#### [Microsoft Defender for Cloud Apps 統合の概要](microsoft-cloud-app-security-integration.md)

### [Windows における情報保護の概要]()
#### [Windows 統合](information-protection-in-windows-overview.md)

### [Microsoft Defender for Endpoint コミュニティ センターにアクセスする](community.md)

### [役に立つリソース](helpful-resources.md)

## [トラブルシューティング]()
### [センサーの状態のトラブルシューティング]()
#### [センサーの状態を確認する](check-sensor-status.md)
#### [異常なセンサーを修正する](fix-unhealthy-sensors.md)
#### [非アクティブ デバイス](fix-unhealthy-sensors.md#inactive-devices)
#### [誤って構成されたデバイス](fix-unhealthy-sensors.md#misconfigured-devices)
#### [イベント ビューアーを使用して、マシン上のセンサー イベントとエラーを確認する](event-error-codes.md)

### [クライアント アナライザーを使用したセンサーの正常性の問題のトラブルシューティング]()
#### [クライアント アナライザーの概要](overview-client-analyzer.md)
#### [クライアント アナライザーのダウンロードと実行](download-client-analyzer.md)
#### [Windows でのクライアント アナライザーの実行](run-analyzer-windows.md)
#### [macOS または Linux でのクライアント アナライザーの実行](run-analyzer-macos-linux.md)
#### [Windows で高度なトラブルシューティングを行うためのデータ収集](data-collection-analyzer.md)
#### [アナライザー HTML レポートの理解](analyzer-report.md)
#### [クライアント アナライザー ツールに関するフィードバックを提供する](analyzer-feedback.md)

 

### [Microsoft Defender for Endpoint サービスに関する問題のトラブルシューティング]()
#### [サービスに関する問題のトラブルシューティング](troubleshoot-mdatp.md)
#### [サービス正常性の確認](service-status.md)
#### [Microsoft Defender for Endpoint サポートに連絡する](contact-support.md)

### [ライブ応答に関する問題のトラブルシューティング](troubleshoot-live-response.md)

### [LiveAnalyzer を使用したサポート ログの収集](troubleshoot-collect-support-log.md)

### [攻撃面の減少に関する問題のトラブルシューティング]()
#### [ネットワーク保護](troubleshoot-np.md)
#### [攻撃面の減少ルール](troubleshoot-asr.md)
#### [攻撃面の減少ルールに以降する](migrating-asr-rules.md)

# [Microsoft 365 Defender ドキュメント]()
## [Microsoft 365 Defender](../defender/index.yml)
## [Defender for Office 365](../office-365-security/index.yml)
## [Defender for Identity](/defender-for-identity/)
